---
id: 515
title: Drawings in Navisworks
date: 2014-08-02T08:00:03+00:00
author: Simon Moreau
layout: post
guid: https://www.bim42.com/?p=515
permalink: /2014/08/drawings-in-navisworks/
categories:
  - Coordination
image: /assets/2014/08/example.jpg
tags:
  - Autodesk
  - BIM Manager
  - DWF
  - Navisworks
---
One of the main complain I heard from Navisworks is to only be able to see a 3D view of the model and not the drawings created from it. It is why I use Design Review to review drawings produced within Revit.

On the other hand, Design Review is generally not powerful enough to display large 3D models, and in this case, Navisworks has to be used.

I recently discover a solution for combining the best of these two applications by integrating DWF files in Navisworks.

To showcase this function, I create a new Navisworks model and append a Revit model in it.

![example]({{ "/assets/2014/08/example.jpg" | absolute_url }})

To be able to see sheets produced within the Revit model, I export them in a new DWF file from Revit:

![dwf]({{ "/assets/2014/08/dwf.jpg" | absolute_url }})

This DWF file can be loaded into Navisworks through the Broject Browser menu. Just hit the Import Sheets & Models button to load the content of this DWF file. We can see its sheets displayed in the Project Browser window:

![projectBrowser]({{ "/assets/2014/08/projectBrowser.jpg" | absolute_url }})

After a right-click -> Prepare All Sheets/Models, we can display these drawings in Navisworks just like in Design Review:

![sheets]({{ "/assets/2014/08/sheets.jpg" | absolute_url }})

Every element in these views is selectable, and its properties are displayed as well.

An interesting feature is the ability to select an element and display it in another view. Just select the element, right-click and hit Find Item in Other Sheets and Models. Navisworks display every views were we can find the selected element.

![find]({{ "/assets/2014/08/find.jpg" | absolute_url }})

This feature present in Revit was missing in Design Review and allows for a quick review of elements from the drawings to the 3D view. On the other hand, some markup tools present in Design Review are not available in Navisworks, and we don't have the ability to import these markup back in Revit.