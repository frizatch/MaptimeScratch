# Blender: Making topographic relief beautiful

![Blender hillshade example](images/1_BlenderHSBanner.png)

![Blender logo](images/1_Blender_logo_no_text.png)

## Tutorial Overview
Blender is a complex, opensource 3D animation software that we can use for rendering digital elevation models for beautiful relief cartography and scene building. The advantage of Blender is it’s built for flexible light simulation so we can create more realistic visuals on our landscape within this software relative to GIS platforms.

The UI for Blender is overwhelming (SO MANY THINGS!), but this tutorial is meant to direct you to the bits you need for topographic rendering.

This exercise follows an excellent and more detailed tutorial by Daniel Huffman, but I've pulled out the skeleton of his workflow and updated the visuals with the 2.8 release UI and and nuances. For more in-depth discussion of what we're doing, please see his tutorial for 2.79 (He'll be updating for 2.8 soon!) it's excellent: [Huffman Tutorial](https://somethingaboutmaps.wordpress.com/2017/11/16/creating-shaded-relief-in-blender/)

What we'll do:

- Touch on prepping digital elevation data
- Get oriented to Blender’s UI
- Build a "mesh" that we mold with our elevation data
- Construct our “photography studio” to highlight our topography with our desired perspective
- Final product: a Blender file that will let us easily create a hillshade for any DEM we want!

## Set up

**Downloading**

* [Blender download](https://www.blender.org/)

Get 2.8! This new, and very different version has a much slicker interface and many of the odd hangups from previous releases have been happily tweaked, so we don't have to do all the steps that 2.79 required.

In the next section, we'll briefly discuss how to prep a height map to use in Blender, but there are two provided for you in this tutorial to get you started in the data folder:

AOI_SouthArapahoePeak	(xxx x xxxxx)
HuffmanDEM.tif		(2000 x 2800 pixels)

*know which one you're using because the dimensions are important!


*DEM*
* Resolution
* Format
* more...

## Creating our landscape mesh
Plane
		render
	Location and size
	Assigning a Material
  In order to have our elevation information actually mold our mesh to respresent the landscape, we need to displace the mesh from the flat plane. Blender has many ways of working with making mesh surfaces "bumpy", but we want to force true displacement. So under the "Material" properties, look for the setting "Displacement" and change it from *Default* to *Displacement*:
  
![](images/Blender_____.png)  
  
Adding dimension – image texture
	Subdividing surface
	UV discussion (quick)
		render
	
## Adjusting our View

## Adjusting our Light Source

