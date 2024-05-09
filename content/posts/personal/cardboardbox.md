---
title: "Cardboard Box Model"
draft: false
categories: ["Personal Projects"]
cover:
    image: "images/projects/cardboardBox/box.png"
    alt: "A model of a box I made in blender"
summary: I made this model with performance in mind. It's purpose is to look as realistic as possible with a minimal amount of vertices.
ShowToc: false
TocOpen: true
weight: 5
---

# The idea
This box was made by me because a friend was making a factory game in which boxes are produced. In this game there are a lot of boxes on the screen at once so it was important that the boxes are as optimized as possible. On top of this the boxes also needed to be made in a realistic style to fit the style of the game.

So the requirements are:
- Optimized mesh 
- Realistic texture
- Highly detailed

# Process
I started by making a high resolution mesh of a box. Making sure to model both the label and the lid of the box. For the tape I wanted to use a cloth simulation to get some nice creases and deformations in the mesh. I also added a small perlin noise displacement to the box to add some irregularities to the normals. 

{{<figure src="/images/projects/cardboardBox/CartonBoxHighResWireframe.png" align=left height=600 title="The wireframes of the detailed model" >}}

After that I baked the normals of the high resolution mesh onto a default blender cube mesh. 
By duplicating the normals and drawing over them in GIMP I was able to easily create a roughness map to make the plastic more reflective then the cardboard. 
For the texture I used an image of cardboard from the internet that I tiled seamlessly and added some small tweaks. I then darkened the parts with tape and added some small noise to the side of the lid. 

{{<figure src="/images/projects/cardboardBox/Box_Color.png" align=left height=200 title="Albedo map of box" >}}
{{<figure src="/images/projects/cardboardBox/Box_Normal.png" align=left height=200 title="Normal map of box" >}}
{{<figure src="/images/projects/cardboardBox/Box_Specular.png" align=left height=200 title="Roughness map of box" >}}


# Result
{{<figure src="/images/projects/cardboardBox/CartonBoxResult.png" align=left height=600 title="A render of the finished box" >}}
