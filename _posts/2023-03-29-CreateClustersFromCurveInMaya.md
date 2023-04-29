---
title: "Create Clusters with MEL and Python in Maya"
date: 2023-03-29
---

Need a way to select a curve and generate clusters at each control point. The following provides a set of clusters that cover control points.

```
# Select a curve and generate clusters at each control point

import maya.cmds as cmds

# Get the selected curve
sel = cmds.ls(sl=True)

# Get the number of spans on the curve
# https://download.autodesk.com/global/docs/maya2012/en_us/index.html?url=files/Editing_NURBS_Change_a_curve_or_surface_s_degree_or_number_of_spans_patches.htm,topicNumber=d28e165949
numSpans = cmds.getAttr(sel[0] + '.spans')

# Get degree of the curve
degree = cmds.getAttr(sel[0] + '.degree')

# Get the maxValue of the curve
maxValue = cmds.getAttr(sel[0] + '.maxValue')

# Get the editpoints of the curve
editPoints = cmds.getAttr(sel[0] + '.editPoints')

# Get the number of control vertices per spans
# The number of CVs is equal to the degree of the curve plus one
# See https://download.autodesk.com/global/docs/maya2012/en_us/index.html?url=files/Editing_NURBS_Change_a_curve_or_surface_s_degree_or_number_of_spans_patches.htm,topicNumber=d28e165949
numCVsPerSpans = degree + 1

# Get Total number of control vertices
numCVs = numSpans * numCVsPerSpans

# Get control points of the curve
controlPoints = cmds.getAttr(sel[0] + '.controlPoints')
 
# Cluster the first span of the curve
cmds.cluster(sel[0] + '.cv[0:1]')

firstClusterCVEnd = 2
cvIndex = firstClusterCVEnd

# Cluster the spans of the curve
# Cluster the degree amount of spans at a time
for i in range(firstClusterCVEnd, int(maxValue) + 1):
    cmds.cluster(sel[0] + '.cv[' + str(cvIndex) + ':' + str(cvIndex + degree - 1) + ']')
    cvIndex += degree
    

# To find out available attributes from command line
# https://help.autodesk.com/cloudhelp/2017/ENU/Maya-Tech-Docs/Commands/listAttr.html
# Examples:
# listAttr bezier1
# listAttr bezierShape1.editPoints
# listAttr -shortNames bezier1

# print number of cvs
print(f"Number of Control vertices: {numCVs}")
print(f"Max Value of the Curve: {maxValue}")
print(f"Control Points of the Curve: {len(controlPoints)}")



```
