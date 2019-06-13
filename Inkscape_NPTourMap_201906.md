# Making Maps Pretty with Inkscape

*This workflow is a copy of Michele Tobias' excellent OpenSourceCartography workshop created for [FOSS4G 2017](http://2017.foss4g.org), Boston, MA, USA*

## Description in Michele's words:
Maps built in the map composer of any GIS program often have the signature look of their software of origin. With some help from graphic design software, maps can have the signature of their cartographer instead. Participants in this workshop will leave with a clear understanding of how to use Inkscape to refine static cartographic works started in QGIS. This workshop will give participants hands-on experience with the workflow presented at the 2016 FOSS4G North America meeting for using QGIS-generated SVG files in Inkscape, including how to build a basic map in QGIS, import it into Inkscape, and work with tools such as fonts, design elements, and alignment tools, to make a map that is truly their own style.

## Our Plan:
We're going to build a map of a tour of National Parks in the Western U.S.!

1. Use Inkscape to make a custom symbol to use for our park locations
  
2. Work in QGIS to build a basic map for our structure
  
3. Pull our QGIS map back into Inkscape to become familiar with layers and refine our map
      
1. Finishing Details in Inkscape
   
## Getting Started
You should already have installed:
* QGIS (3.4)
* Inkscape (0.92.2)

## Data
Data to use in this workshop is in the [Data Folder](https://github.com/AL-RSS/MaptimeTutorials/tree/master/Inkscape2019-master)

## Intro to Inkscape
### Inkscape is a vector graphics progam ... you know, vector data!
   1. Concept of vectors (points, lines, polygons) vs. rasters (images)
   1. Window Overview
   1. GIS-Similar Concepts
       1. Merge/Clip/Union/Etc.
       1. Layers
       1. Fill & Stroke = Symbology
       
### Make Your Own Tree Icon in Inkscape
Let's learn to use Inkscape while making something we can use later: an icon to represent a point.  I'll walk you through how to make a map pin icon, but feel free to make your own version!  *Something to remember: SAVE OFTEN! Just like GIS, vector illustration programs can be a little unstable. Save every time you think you might want to.*

Open Inkscape.  Let's learn a little about the interface.
![Inkscape Interface Tour](/Images/InkscapeTour.png)

There are a lot of toolbars.  Here are some tools you might need:
![Toolbars Cheatsheet](/Images/Toolbars.png)
Use these images as a guide to help you find the tools we're using.

For our tree top, we'll draw a triangle with the Bezier curves and straight line tool ![Bezier Tool](Images/Tool_Bezier.PNG) icon. If you prefer a round/deciduous tree, draw a circle in the middle of your canvas using the Cirlce & Elipse tool: click on the ![Circle Tool](/Images/Tool_Circle.PNG) icon. Hold down Ctrl while drawing your circle to make a perfect circle (instead of an elipse which is longer in one dimension).  Save.

![Draw a Circle](/Images/Pin_1_Circle.png)

Select your cirle with the Select & Transform Objects tool ![Select Tool](/Images/Tool_Select.PNG) and then Open the Fill & Stroke dialog. ![Fill and Stroke Dialog](/Images/Tool_FillStroke.PNG)  You can set the fill & stroke either in this dialog or on the pallette at the bottom of the screen. Set the fill to an orange color and the stroke to a darker orange.  Save.

![Make the Circle Orange](/Images/Pin_2_OrangeCircle.png)

Now use the rectangle tool ![Rectangle Tool](/Images/Tool_Rectangle.PNG) to draw a skinny, tall rectangle. Make the fill a medium gray and the stroke a dark gray.  Save.

![Add a Gray Rectangle](/Images/Pin_3_Rectangle.png)

It doesn't look much like a tree yet because we need to stick the top and trunk together. Open the Align & Distribute dialog. ![Align Tool](/Images/Tool_Align.PNG) Select your circle with the Select tool, then hold down Shift and select the rectangle.  Now both the circle and rectangle are selected.  Change the drop-down in the Align dialog to "First Selected" and the click the button to "Center on Vertical Axis" (hover over the buttons to get a tool tip with the name of the buttons).  Now your rectangle should be in the middle of your circle.  Save.

![Align objects](/Images/Pin_4_Align.png)

You'll probably want to move the rectangle so it's near the bottom of the circle.  Select the rectangle and use the arrow keys on your keyboard to move it down.  Hold Shift with the arrow keys to move objects in larger jumps.    Save.

![Align objects](/Images/Pin_5_Move.png)

It's looking better!  But the rectangle should really be underneath the circle.  Select the rectangle.  On the left side above the canvas, you'll see that the tool bar has options to raise and lower items relative to each other.  Use "Lower Selection to Bottom" ![Send to Back Tool](/Images/Tool_SendToBack.PNG) to put the rectangle below the circle.  Now it's really starting to look like a pin!  Save.

![Change the order](/Images/Pin_6_Order.png)

We could use our drawing just the way it is, but let's add a few more elements to make it look more realistic and to learn a few more tools.  First, let's give the pin's stem some dimension by rounding the end of the rectangle.  Select the rectangle and read the text at the bottom of the screen: "**Rectangle** in layer **Layer 1**."  This tells us that the type of object we've selected is a rectangle.  To edit the rectangle more than just changing it's size, we'll need to turn it into a Path.  With the rectangle selected, click the Path menu at the top of the screen and select "Object to Path".  Notice that the text at the bottom of the screen now tells us that our object is a "path" with 4 nodes.  

Select the Node Editing tool ![Node Tool](/Images/Tool_Node.PNG), then click on the rectangle.  You should see that each corner now has a little diamond-shaped node.

![Nodes Active](/Images/Pin_7_NodesActive.PNG)

With the node tool still active, click on the line segment between the bottom two nodes. The two bottom nodes will be highlighted to show they are selected (they turn blue on my personal computer, but that might vary depending on operating system and such).

![Selected Nodes](/Images/Pin_8_SelectedNodes.PNG)

The tool menu above your canvas has changed to show tools relevant to working with nodes.  Click the button to "Make Selected Segments Curves" ![Curve Segments Tool](/Images/Tool_CurveSegment.PNG).  Little circles will appear to indicate the Bezier curve handles, but they are hard to see since they are inline with the bottom of the rectangle.  Zooming in with the zoom settings in the lower right corner of the screen can help.  Click one handle and drag it to see how it affects the line segment.  Adjust both handles to make a relatively symetrical curve at the bottom of your pin.  Save.

![Curve Handles](/Images/Pin_9_CurveHandles.PNG)

Let's make the pin look shiny.  This will be a good opportunity to test out some of the things you've learned.  Using the Pen (Bezier Curve) Tool ![Pen Tool](/Images/Tool_Bezier.PNG), draw an elongated triangle along the upper left side of the pin - one click for each corner of the triangle and a final 4th click on the first corner to close up the polygon.  Select your new triangle with the selection tool (the arrow) to make it active, then change the fill to a light orange.  You can either remove the stroke or set it to the same light orange color.  Save.

![Triangle Shine](/Images/Pin_10_TriangleShine.PNG)

Using the Node Tool like before, round the two longer sides to make the pin look curved.  Save.

![Curved Triangle](/Images/Pin_11_CurvedTriangle.PNG)

And add some shine to the pin stem with a smaller rectangle of a lighter gray on top of your pin's stem. Curve the top and bottom edges to make it look 3 dimensional.  Save.

![All Done](/Images/Pin_12_Finished.png)

Adjust the page size: In the File menu, click on Document Properties.  In the Custom Size section, expand the "Resize page to content..." section by clicking on the little + sign.  Make sure nothing in your drawing is selected by clicking in a blank space.  Click the "Resize page to drawing or selection" button.  The page boundary should now hug the edge of your drawing.  Save one final time, close Inkscape, and you'll be ready to use your new pin marker in QGIS!

  
## Working in QGIS
Open QGIS

### Load Data
Import the vector data you would like to work with. Use the Data Source Manager ![Data Source Manager](/Images/QGISTool_DataSourceManager.PNG) to import data:
* From this repository's [data folder](/Data): FOSS4G_Locations_2018.geojson (locations of all of the FOSS4G conferences) and either the FOSS4G_Lines_2018.geojson (straight lines between the conference locations) or FOSS4G_GreatCircles_2018.geojson (great circle lines between the locations). 
* From the internet: [Natural Earth Country' 1:110m Cultural Admin-0 Country Boundaries](http://www.naturalearthdata.com/downloads/110m-cultural-vectors) and any other data you would like to add to your map (such as the Admin-1 States & Provinces Natural Earth data).

Order your layers in the Layers panel so that the countries on the bottom, then the lines, and points on top.  Save your work.

![QGIS Layers Loaded](/Images/QGIS_1_LayersLoaded.PNG)

### Working with Standard Symbology

Let's start by changing the colors of our country polygons layer.  
1. In the Layers panel, right click on the country polygons layer and select Properties from the menu.  
1. In the Layer Properties window, click on the Symbolgy tab on the left side.  We'll leave our polygons as "Single Symbol" for now, but you can look at all the options on the this drop down to see what the possibilities are.  
1. In the box below, click the "Simple Fill" layer.  Pick a fill color and a stroke (outline) color.  Adjust the stroke width as well if you would like.

### Use Custom SVG Markers in QGIS

Let's use the tree marker we made earlier as the marker for our point layer: 
1. Open the layer properties for the point layer and click on the Symbology tab on the left side of the window.  
1. In the main part of the properties window, you'll see that your point layer was set by default to a "Simple marker".  Click on the "Simple marker" text in the white box to access options for changing the marker type.  
1. In the "Symbol layer type" drop down, select "SVG marker".  
1. You will probably need to scroll down in the window to see the SVG Groups and SVG Images section of the dialog.  Click the "..." button and navigate to where you saved your pin SVG file.  Select your file and click the "open" button.  (Alternatively you can put it in your User Symbols folder for QGIS to see it in the User Symbols SVG Group tree.)  The marker preview at the top of the window should have changed to a pin.  
1. Click "Apply" to see how it looks on your map.  Adjust the size of your pin marker to any size you like.  You can always make adjustments later.  In the size adjustment options, notice that if the "lock aspect ratio" lock image is closed, the aspect ration will be preserved.  If the image shows an open lock, you can make the image thinner or wider by changing the height or width independently.  Click "OK" to exit the dialog.
1. Save your work.

![Point Marker Dialog](/Images/QGIS_2_PointMarkerDialog.PNG)

![Pins on the Map](/Images/QGIS_3_PinsApplied.PNG)

You can also use SVG markers for lines.  The process is similar to what you just did with your point markers: make the SVG marker in Inkscape, load it into QGIS in the layer properties dialog, and set some parameters.  To save some time, I pre-made an SVG for you to try with your lines layer that looks like a single twist of rope.  You can use this to make your line look like string.
1. Find the Rope_Segment.svg file in the [Pre-Made SVGs Folder](/Pre-Made_SVGs) of this repository.  You'll also see that there's a pin svg in case you want to see what my version looks like.  Alternatively, you can make your own rope segment in Inkscape using the skills you just learned with the Pen Tool and Node Editor to make a similar shape.  The key to success is to make sure the left and right side of the shape fit together well when the image is repeated next to each other.  It's fiddly so I made one for you.
1. Open the Layer Properties dialog for the lines layer and go to the Symbology tab, just like before.
1. In the white box, click on the "Simple line" text.
1. In the "Symbol layer type" drop-down menu, pick "Marker line".  Notice that you have a longer tree of layers in the white box.
1. In the white box, click the "Simple marker" text.
1. Change the "Symbol layer type" drop-down menu selection to "SVG marker".
1. Similar to what we did before, use the "..." button to open the dialog to find and select your Rope_Segment.svg and click the "Open" button.  It may be hard to see since the rope segment colors are similar to the dialog box, but you should see what looks like a tan dashed line in the preview.
1. Adjust the size of the segments in the "Size" parameter box.  I used a width of 4 milimeters to be able to see the segments.  They don't fit together yet, but we'll fix that next.
1. Up at the top of the dialog, in the white box, click on the "Marker line" text.  The radio button next to "with interval" should be selected.  Change the spacing to make no space between the segments. 1.6 milimeters worked for me.  Apply these changes to the canvas with the "Apply" button.  If you like what you see, click "OK" to close the dialog, otherwise, make some more adjustments.  NOTE: A process similar to what we just did [can also be done in Inkscape](https://inkscapetutorials.org/2014/10/20/use-inkscape-to-draw-vector-rope-in-any-shape/), but it tends to work better on gentle curves.

![String Lines](/Images/QGIS_4_String.PNG)

## Compose Your Map

At this point, you'll want to get an idea of what your final map will look like.  I sometimes use a [Google Image](https://images.google.com) search to get some ideas.  For example, if you want to continue with the map pin board theme, try googling related keywords to see what kinds of map pin boards there are.  Do you want to label the locations?  Do you want lines for states and provinces?  Maybe you want some city names or graticule lines?  Get everything into the canvas you think you'll need for your final map.  It doesn't have to look nice at all yet, but unless you want to add it by hand later, you'll want to put it in now.

Let's add labels to our points.  
1. Open the layer properties for your point layer.
1. Click on the "Labels" tab.  On the drop-down menu, select "Single Labels".
1. If we just want to label the points with the conference name, from the "Label With" drop-down, chose "Event".  
1. Click "Apply" to see what that looks like.

Ok, that's good so far, but let's add the event location to the label as well.
1. On the far right side of the "Label With" drop-down menu, click the Epsilon button (it looks like a script upper case E) to open the Expression Dialog.
1. Delete any text in the expression box.
1. To the right of the expression box, expand the "Fields & Values" list.
1. Double click on "Event"  to add this field to the expression box.
1. Because we are building a string, we will combine the elements of the string with the concatenation characters ||.  Click the || button above the expression box, then the new line ('\n') button, and || again - this adds a new line to our labels.
1. Finally, add the "Location" field from the list of "Fields & Values" list, like before.
1. The string you built should read: ` "Event"  ||'\n'||  "Location" `  If there is an error, the message will appear below the expression box.  Click Ok when you've finished building your query.
1. In the Layer Properties dialog, adjust the font and font size to your liking.
1. Let's make sure all our labels will show up in our map.  In the Labels tab of the Layer Properties dialog, cick on the Rendering option inside the long white box.  Check the box for "Show all labels for this layer (including colliding labels)".
1. Explore any other options you would like to try.
1. When you're finished making adjustments, click OK.

Helpful Links:
* [Multiline Labels in QGIS](https://anitagraser.com/2011/06/15/multi-line-labels-in-qgis/) from Anita Graser
* [QGIS Training Manual Print Composer Tutorial](http://docs.qgis.org/2.14/en/docs/training_manual/map_composer/index.html)

![Labels Added](/Images/QGIS_5_Labels.PNG)

## Compose Your Map
We've added all the layers we need in our map and added labels for the point locations.  Now we need to compose a map.  We'll use the Map Composer to create a layout that generally looks the way you want it to.  

First, we have to make a new layout to work with:
1. Click on the Project menu at the upper left corner of the QGIS window, then select New Print Layout.
1. In the Create Print Layout Title window, enter a title for your layout in the box.  I'll use "FOSS4G Map" so I'll remember later what my map layout was for.  Click OK.

Now we can compose our map. 
1. Add your map to the page: from the Add Item menu, select Add Map to enable the Add Map Tool.
1. While clicking on the page, drag your mouse across the page to add the map.
1. To resize the map box, use the Select/Move Item (it looks like white arrow), then drag the resizing handles.

Now we have a map, but the scale probably needs to be adjusted.
1. Select the map item using the Select/Move Item tool.
1. On the right side of the window, click on the Item Properties tab.
1. Adjust the number in the Scale box to zoom in or out of your map data.  Smaller numbers zoom in; larger numbers zoom out.  Set the extent and scale of the map to roughly what you anticipate needing for the final product.  When in doubt, pick a larger scale (more zoomed out) because we can always trim away extra, but we can't add it back easily in Inkscape later.  
1. You can pan the map data using the Move Item Conent tool - it looks like a  curled page with blue arrows on it.

All items you add to your map composition have properties, just like this map item.  If you add a scale bar or a legend, for example, you can change their appearance by selecting them and making changes to the Item Properties.

At this point, you should have a map composition that has all the data (probably the country boundaries and the point locations, and perhaps the lines) and labels you want in your final map as well as any other items you want to add.  It does not matter if your labels run off the page or collide with each other, but make sure they are all showing.    

![QGIS Print Composer](/Images/QGIS_6_MapComposer.PNG)

## Export SVG

When you've got the layout generally how you want it, click the "Export to SVG" button.  ![Export to SVG Button](/Images/Tool_ExportToSVG.PNG) Ignore the warning.  (You'll see what the warning is talking about soon, but it's not really a problem... and perhaps it's even a feature once you know how to deal with it.)  Navigate to where you want to save your file, name it, and click the "Save" button.  Uncheck "Export map layers as groups" and "Render map labels as outlines", then click "Save".  

Now we're ready to start refining this map in Inkscape!
      
## Finishing Details in Inkscape

Open your map file in Inkscape:
1. Start Inkscape
1. File menu -> Open
1. Navigate to your file and then click "Open"

Your map may look a little rough right now.  Mine, for example, has text running off the page and the colors are not probably going to stay the way they are.  That's ok.  Now's a good time though to think again about if there's anything else you'd like to add.  It's easier to make a new file in the QGIS Print Composer now than to try to add things later.

Unlike the previous sections of this workshop, finishing your map in Inkscape doesn't have a prescribed set of steps.  Next we'll go through some tools and suggestions for how they can help, but how you apply them and the order in which you apply them is largely up to you and your artistic sensibilities.

**Grouping**  Grouping ![Group Tool](/Images/Tool_Group.PNG) and ungrouping ![Ungroup Tool](/Images/Tool_Ungroup.PNG) are useful tools.  Grouping objects allows you to treat multiple objects as one until they are ungrouped.  Typically, .svg files exported from QGIS have all of the vectors grouped into one massive group with subgroups.  

Before we can edit anything, we'll need to ungroup the big single group: Using the Select Tool ![Select Tool](/Images/Tool_Select.PNG), click on some part of the drawing on your canvas.  Look at the bottom of the window and verify that you've selected a group.  The text on the bottom of the window will say something like "Group of 15000 objects in root".  Now ungroup using the Ungroup tool ![Ungroup Tool](/Images/Tool_Ungroup.PNG).  It may take a while for this process to finish because we have so many nodes.  Save.

**Layers**  Another helpful feature of Inkscape is the ability to put items into different layers.  This concept is very similar to what you're already familiar with in GIS.  Layers higher in the list sit on top of layers that are lower in the list.  Layers can be turned on and off to limit what you see but also to reduce the loading time as you work on items in a different layer.  Usually .svg files saved from QGIS don't have any layers assigned.  I like to make one layer to start and move everything into this layer.  Then I add more layers as needed to issolate different elements of my map.  For example, I typically put all the labels in one layer, all the country polygons in another, and the text and title in another.

Let's make that first layer to hold everything until we decide to move it:
1. Open the Layers dialog. ![Layers Button](/Images/Tool_Layers.PNG)  If it docks to the side of the window and the dialog is too small, hover your mouse cursor over the bottom edge of the dialog below the Opacity slider to see the cursor that will let you click and drag to expand the window.
1. Click the + button to add a layer.  A pop-up will ask you what you want to call it.  I like to call mine something like "Everything Else" since I'll be moving some items out but maybe not everything.
1. Nothing is in this layer yet, so let's move all the items in the canvas into it. Select everything with either Ctrl + a on the keyboard or "Select All" from the Edit menu.  Right click on any item, and select "Move to layer" from the menu that comes up.  This option can also be found in the Layer menu at the top of the screen.  Pick the layer you want to move the items to - in this case "Everything Else" - and click the "Move" button.  Inkscape may take a minute to finish this process.  Save when it's done.  You can confirm that the items have moved into this layer by click on the the button that looks like a tiny eye to turn off the visibility.  If everything disappears, it moved.  Turn it back on, and everything should be visible again.

Add layers as you need them.  Right now, similar things tend to be grouped because that's how QGIS exports them.  For example, you can easily select all of the country polygons right now because they are in one group, which makes it easy to move them into their own layer right now.  Once they are ungrouped, if you don't want to have to select them all individually, there's a handy trick: Right click on one of the items and click "Select Same" from the menu that appears.  Pick the option that will select all of the similar items.  For example, my country polygons all have the same fill.  Once they are all selected, you can move them into a new layer.

![Layers](/Images/Inkscape_1_Layers1.PNG) 

![Layers](/Images/Inkscape_1_Layers2.PNG) 

![Layers](/Images/Inkscape_1_Layers3.PNG) 

![Layers](/Images/Inkscape_1_Layers4.PNG)

**Text**

Fortunately now when you export .sgv files from QGIS, the labels now import into Inkscape as text.  Text, like polygons, in Inkscape can have both a fill and stroke (use the Fill & Stroke Tool ![Fill & Stroke](/Images/Tool_FillStroke.PNG)) and the text can be edited to make adjustments.  Be careful not to ungroup text.  If you ungroup text, it will turn into a path, which has advantages if you want to get creative, but you won't be able to change the letters by typing into a box any more.

Edit existing text by selecting it and then opening the text dialog. ![Text Dialog](/Images/Tool_TextDialog.PNG)

Add new text by using the text tool. ![Add Text](/Images/Tool_Text.PNG)  Text you might want to add to your map includes things like a title, cartographer information, data credit, and maybe some information about the points.

**Copy & Paste**

It might seem obvious that you can copy, cut, and paste in Inkscape (of course you can!) but there's also specialized options for graphics that you won't find in other programs:
* "Paste in Place" - File menu or Keyboard Shortcut: Ctrl + Alt + v - paste an object copied to the clipboard in exactly the same place that it was copied from.  I use it for making halos around text.  Copy the text, paste it in place, make the copy white (or the color you want), give it a blur in the Fill & Stroke dialog, then lower it below your regular text.
* "Paste Style" - File menu
* "Paste Size" - File menu - has a variety of options for which dimension to paste
* You can also paste a color into either the Fill or Stroke of an object either by copying it from Inkscape or using a tool like the [Colorzilla](http://www.colorzilla.com/) extension for Chrome and Firefox.
* Use the Eyedropper tool to select a color on your canvas to automatically copy into the Fill or Stroke (hold shift when you click)

**Clip**

Clip is helpful for dealing with those polygons that didn't get clipped properly in the QGIS export.  You'll find the Clip tool in the Object menu at the top of the screen.  Select the item or group of items you want to clip, along with the polygon you want to clip with, then set the clip.  One of the nice things about Clip in Inkscape is that you can set and release it, so if you need to make adjustments later, undo it by releasing your clip.

Clip can also be used on images to cut out any polygon shape.  It works just like clipping a raster in a GIS.

**Other Things to Consider** 
* Move your labels around so you can see them all clearly
* You might need to move some of your pin markers to make them move visible (the pins in the US' midwest are almost on top of each other).
* Maybe your strings need a drop shadow. (Group all your segments, then Filters menu -> Glows & Shadows -> Drop Shadow) 
* Explore the Filters and Extensions menus.

**Export**

When you're all done, you'll want to save your map in an image format.

In the File menu at the top of the screen, you'll find the "Export PNG Image" option.  In this dialog you have choices about what part of the drawing to export (the extent of the page, the extent of selected objects, etc.).  Pay attention to this because if you have something selected, it might assume you want to use this extent for your export.

Another option for different file types is the "Save As" option in the File menu.  There are a multitude of options here including PDF.

## Example

Here's an example of a map I created with the same data you're working with.  I liked the idea of the textured string, but it was just too cluttered for my map, so I left it out.  I've included annotations on my map so you can learn how the effects were done.  None of it is fancy or difficult.  It's mostly just layering items.
![Example Map with Annotations](/Images/PinMap_Annotations.png)
