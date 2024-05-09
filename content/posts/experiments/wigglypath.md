---
title: "Wiggly Path Generator"
draft: false
categories: ["Experiments"]
cover:
    image: "images/projects/wigglypath/TerrainPathGenerated.png"
    alt: "A generated path that follows the terrain"
ShowToc: true
TocOpen: true
weight: 20
---

For Golf Rush I was researching different ways to
point out to players where the golfball is located.
One of these experiments was inspired by the way
Hogwarts Legacy points you to quests. With a
generated curvy line moving towards the goal.
It works by inputting some points to generate a
simple bezier curve and then placing knots on that
simple curve that are offset randomly along the
normal. Then finally all the knots are connected by
one last bezier curve. To make the line go through
all important knots, guides are generated along the
tangent.


### Basic Bezier
I started by creating a basic implementation of [quadratic bezier curves](https://en.wikipedia.org/wiki/B%C3%A9zier_curve#Quadratic_B%C3%A9zier_curves) that is rendered by sampling at a specified resolution (128 for all examples) and adding those points to a Unity LineRenderer component.
> {{<figure src="/images/projects/wigglypath/BezierCurveGenerated.png" align=left width=500 >}}

### Curvy Path 
After the basic Bezier was working I wrote a script to automatically generate the knots inbetween two points and offset those along the normal of the curve. The normal is calculated by getting the derivitive of the bezier curve and turning that vector 90 degrees using: (x, y) =*rotated 90 degrees*=> (-y, x).
> {{<figure src="/images/projects/wigglypath/CurvyPathGenerated.png" align=left width=500 >}}

### Meandering Path
To add more control over the path I added the option to add more control points apart from the start and end points.
> {{<figure src="/images/projects/wigglypath/PathGeneratorShowcase.gif" align=left width=500 >}}

### Terrain Path
The last thing I added: making the height of the curve dependant on the height of the Unity Terrain component below that part of the curve, so that it could follow the terrain. 
As well as a texture for the LineRenderer so that it looks like a dotted line.
> {{<figure src="/images/projects/wigglypath/TerrainPathGenerated.png" align=left width=500 >}}

