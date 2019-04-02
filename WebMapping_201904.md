# Web Mapping: Playing with Leaflet and qgis2web

## What is a web map anyway? (Digitized maps vs. web maps)

![a static map](images/parkingmeter-staticheatmap.png)  ![a dynamic map](images/parkingmeter-webheatmap.gif)

Web maps, or slippy maps, are based on tiles that load on demand so you limit the data you use to the data you need to see. For more orientation to how they are structured (zoom levels and distibutions) visit this [wikipage](https://wiki.openstreetmap.org/wiki/Slippy_map_tilenames)

# What do we need to make them?
# PART I: Leaflet

- A Web Browser
- A Text Editor
- Directories, Files, Data and Media
- Web Server
- Web Developer Tools

## Set up

The first thing we need to do to create a web map using Leaflet is to set up a development environment. This allows you to write code and test how your map looks and works.

**A Web Browser**

While were making a map to be seen in a browser, we use a brower. Pretty simple. But not all browsers are created equally. Use Chrome or Firefox when you're doing web development.

**A Text Editor**

To use Leaflet to build our webmap, we'll be working directly in text. You'll want a text editor that helps you see code easily by highlighting the different functions of the syntax. These three are are commonly used:

* [Brackets](http://brackets.io/)
* [Sublime](https://www.sublimetext.com/)
* [Atom](https://atom.io/)

If you don't want to bother with setting up a local server, use Brackets! Its "Live Preview" functionality runs a local test server for you within your web browser. You'll see a new browser window pop up where you can see and test your application.


**A Web Server**

A "server" is needed to gather the files and deliver them to the browser correctly so the brower can properly interpret and render the information. For example, a server is necessary when using JavaScript to make what are known as [asynchronous requests](http://rowanmanning.com/posts/javascript-for-beginners-async/) to load files and data into our web application after the web page initially loads.

When we put together a web map, we test it on our own computer before serving it to the web, thus the need for a "local server." Here is a nice [gist](https://gist.github.com/jgravois/5e73b56fa7756fd00b89) for setting up a local server on your machine.

OR, as mentioned, the [Brackets](http://brackets.io) text editor allows you to bypass this because it runs "Live Preview".


## Okay, let's make a map! But wait. What IS Leaflet?

Leaflet is an open-source JavaScript library for mobile-friendly interactive maps.

Let's take a look at how it works with a simple simple webmap:

```html
<!DOCTYPE html>
<html>
<head>
  <title>A Leaflet map!</title>
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.4.0/dist/leaflet.css"
    integrity="sha512-puBpdR0798OZvTTbP4A8Ix/l+A4dHDD0DGqYW6RQ+9jxkRFclaxxQb/SJAWZfWAkuyeQUytO7+7N4QKrDh+drA=="
    crossorigin=""/>
  <script src="https://unpkg.com/leaflet@1.4.0/dist/leaflet.js"
    integrity="sha512-QVftwZFqvtRNi0ZyCtsznlKSWOStnDORoefr1enyq5mVL4tmKB3S/EnC3rRJcxCPavG10IcrVGSmPh6Qw5lwrg=="
    crossorigin=""></script>
  <style>
    #map{ width: 900px; height: 500px; }
  </style>
</head>
<body>

  <div id="map"></div>

  <script>

  // initialize the map
  var map = L.map('map').setView([39.75, -105.01], 14);

  // load a tile layer (see http://leaflet-extras.github.io/leaflet-providers/preview/ and copy w/o ""})."" or pick one below)

  // Here's a direct URL Stamen option - replace "toner" here with "terrain" or "watercolor" (watercolor has different attribution, though)
  L.tileLayer('http://tile.stamen.com/terrain/{z}/{x}/{y}.png',
    {
      attribution: 'Map tiles by <a href="http://stamen.com">Stamen Design</a>, under <a href="http://creativecommons.org/licenses/by/3.0">CC BY 3.0</a>. Data by <a href="http://openstreetmap.org">OpenStreetMap</a>, under <a href="http://www.openstreetmap.org/copyright">ODbL</a>',
      maxZoom: 17,
      minZoom: 9
    }).addTo(map);

  </script>
</body>
</html>
```
Within this code we have 3 elements that help create our map:
- [HTML](https://www.w3schools.com/html/default.asp) (structure) - the content of our webpage
- [CSS](https://www.w3schools.com/css/default.asp) (form) - the design of the webpage
- [Javascript](https://www.w3schools.com/js/default.asp) (behavior) - adding the bits that make this a non-static map!

The code in the index.html file in this repo is the same as the above with a few options alternative options added (but commented out) for different base maps. Where might you find these? There are a bunch collected for you on this lovely [webpage](http://leaflet-extras.github.io/leaflet-providers/preview/) where you can click on the thumbnails to get blocks of code to copy and paste.

Now that you have a local server running, open the *index.html* file (or open this file from within Brackets using the Live Preview). See what happens! Change up your tiles and pick a map style you like.

Hint: There are different ways to quickly comment out lines of code or reinstate them. In Atom on a mac, use "command /" after highlighting your lines of interest.

**Adding our own data!**

We can add in another JavaScript library called jquery to help us load GeoJSON data onto our map:

```html
<!DOCTYPE html>
<html>
<head>
  <title>A Leaflet map!</title>
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.4.0/dist/leaflet.css"
    integrity="sha512-puBpdR0798OZvTTbP4A8Ix/l+A4dHDD0DGqYW6RQ+9jxkRFclaxxQb/SJAWZfWAkuyeQUytO7+7N4QKrDh+drA=="
    crossorigin=""/>
  <script src="https://unpkg.com/leaflet@1.4.0/dist/leaflet.js"
    integrity="sha512-QVftwZFqvtRNi0ZyCtsznlKSWOStnDORoefr1enyq5mVL4tmKB3S/EnC3rRJcxCPavG10IcrVGSmPh6Qw5lwrg=="
    crossorigin=""></script>
  <script
    src="https://code.jquery.com/jquery-3.3.1.js"
    integrity="sha256-2Kok7MbOyxpgUVvAk/HJ2jigOSYS2auK4Pfzbm7uH60="
    crossorigin="anonymous"></script>
  <style>
    #map{ width: 900px; height: 500px; }
  </style>
</head>
<body>

  <div id="map"></div>

  <script>

  // initialize the map
  var map = L.map('map').setView([39.75, -105.01], 12);

  // load a tile layer (see http://leaflet-extras.github.io/leaflet-providers/preview/ and copy w/o ""})."" or pick one below)

  // Here's a direct URL Stamen option - replace "toner" here with "terrain" or "watercolor" (watercolor has different attribution, though)
  L.tileLayer('http://tile.stamen.com/terrain/{z}/{x}/{y}.png',
    {
      attribution: 'Map tiles by <a href="http://stamen.com">Stamen Design</a>, under <a href="http://creativecommons.org/licenses/by/3.0">CC BY 3.0</a>. Data by <a href="http://openstreetmap.org">OpenStreetMap</a>, under <a href="http://www.openstreetmap.org/copyright">ODbL</a>',
      maxZoom: 17,
      minZoom: 9
    }).addTo(map);

// load GeoJSON from an external file
$.getJSON("./data/firestations.geojson",function(data){
//  add GeoJSON layer to the map once the file is loaded
L.geoJson(data).addTo(map);
});

</script>
</body>
</html>
```
What is different?

1) We added in another src command to find another JavaScript library called jquery
2) Using the jquery library functions, we added a layer (GeoJSON data) onto our background tiles after retrieving our data.

Also, we changed the zoom level for the map initialization! This gave us a broader view to see more of the fire stations on load.

Note: The data we're using was pulled from the city of Denver's open data [portal](https://www.denvergov.org/opendata/) as shapefiles and then converted to geojson files using QGIS.

# What do we need to make them?
# PART II: qgis2web plugin for QGIS

## Introducing the qgis2web plugin!

For those of you new to QGIS, there is a strong developer community surrounding this open source software and great plugins are continually being created and improved.

We'll be using two plugins:
- QuickMapServices
- qgis2web

To add them to your QGIS, go to the "Plugins" tab on the main menu and select "Manage and Install Plugins..."

A window will open that has many plugin options listed alphabetically. Go to the Q's and install the two mentioned above. Your window should look something like this when they've been added:

![Q.G.I.S. plugins](images/qgis-plugins.png)

The QuickMapServices plugin is a way of quickly adding in basemaps to your project. XYZ tiles is richer way to add basemaps, but we'll stick with adding in the standard OSM basemap for now: from the main menu bar go to Web -> QuickMapServices -> OSM -> OSM Standard.

The qgis2web plugin is a marvelous way of designing our maps in QGIS, then having the work of smushing all the HTML, CSS and JavaScript together done *FOR* us using Leaflet or another library called OpenLayers. These libraries are different and don't work with data and symbology the same way, so play around!

## Create a simple map in QGIS

We've already added a basemap to our project, but let's make our map a little more interesting before we use qgis2web to export our map to the web. One great thing about interactive web maps is the possiblity of pop-ups that show the attribute information behind the features on our map.

Add the data layer parkingmeters.geojson to your QGIS map. You should be able to merely drag it from your folder and drop it into the blank area below the OSM Standard basemap layer.

**Examine your data!**

Once the parkingmeters layer appears in your QGIS contents, right click on the layer and select "Open Attribute Table". Here, you can examine the fields and try to figure out all the information that has been recorded about these spatial features. Of course, if the information is opaque, there should be metadata on the Denver Open data site that explains it better!

**Symbolize your data**

*Simple Symbol*
Right click on the layer again, but this time select "Properties". This will open up a new window with a number of menu options. Pick "Symbology". Keep the default Simple Symbol option for exploring pop-ups, but play with the color and marker options.

*Heat Map*
Alternatively, if you don't want to mess around with pop-ups, on the Symbology pane at the very top, change the Simple Symbol option in the drop down to "Heat Map".  Select the color ramp "Reds" and change the layer rendering's opacity to something less than 100%:

![Options for heat map symbology](images/qgis-heatmapsymbology.png)

**Prepping for pop-ups**

For the pop-ups, we may not want all of the attributes with their default values to show when we hover over our features. We can change the field labels by writing in Aliases in the QGIS Attributes Form, or we can eliminate them by switching the “Widget Type” to “Hidden.” 

![the Attributes Form in QGIS](images/qgis-attributesform.png)

In the example above, the alias for ZONE is written as “Zone” to get rid of the all-caps. If we wanted this field to not show in the pop-up at all, we would use the drop-down to change “Text Edit” to “Hidden.”

The maintainer of qgis2web, Tom Chadwin, has further help for this plugin on his [wiki](https://github.com/tomchadwin/qgis2web/wiki)
