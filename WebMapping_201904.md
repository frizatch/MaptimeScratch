# Web Mapping: Playing with Leaflet and qgis2web

## What is a web map anyway?

**Static Maps vs Web Maps**

## What do we need to make them?

- A Web Browser
- A Text Editor
- Directories, Files, Data and Media
- Web Server
- Web Developer Tools

## Setting up a development environment

There are many [lessons and resources](http://maptime.io/lessons-resources/) available on the web for getting started with web mapping. But often, getting the development environment set up so you can write code and test your map is the first roadblock. Let's consider the principle components of a web development process. These are what you need to have available every time you begin web map design and development.

**A Web Browser**

Web Mapping is an unusual form of Cartography in that we primarily make the maps using the same medium with which we develop them. The web browser is a crucial component of our technology stack. Most web map developers use Chrome or Firefox, as should you. Make sure you have installed recent updates to your browser, and begin by opening your Web Browser.

**A Text Editor**

Developers build web maps by writing plain text. Text editors designed for web development facilitate this, particular by highlighting different parts of the code syntax. Install and open one of the following:

* [Brackets](http://brackets.io/)
* [Sublime](https://www.sublimetext.com/)
* [Atom](https://atom.io/)

If you don't want to bother with setting up a local server, use Brackets! Its "Live Preview" functionality runs a local test server for you within your web browser. You'll see a new browser window pop up where you can see and test your application.


**A Web Server**

While a web browser application interprets and renders the files that compose our web maps, it doesn't do this by itself. It requires a "server" to gather the files and deliver them to the browser correctly. A server is especially necessary when using JavaScript to make what are known as [asynchronous requests](http://rowanmanning.com/posts/javascript-for-beginners-async/) to load files and data into our web application after the web page initially loads.

When we put together a web map, we test it on our own computer before serving it to the web, thus the need for a "local server"

Here is a nice [GUIDE](https://gist.github.com/jgravois/5e73b56fa7756fd00b89) for setting up a local server on your machine.

OR, as mentioned, the [Brackets](http://brackets.io) text editor allows you to bypass this because it runs "Live Preview".

Now that you have a local server running, open the *blahblahblah/index.html* file (or open this file from within Brackets using the Live Preview).

## Okay, let's make a map!

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

Here is the exact same code with a few options added in (but commented out) for different base maps from that resource:

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

  // var Esri_WorldTopoMap = L.tileLayer('https://server.arcgisonline.com/ArcGIS/rest/services/World_Topo_Map/MapServer/tile/{z}/{y}/{x}', {
  // 	attribution: 'Tiles &copy; Esri &mdash; Esri, DeLorme, NAVTEQ, TomTom, Intermap, iPC, USGS, FAO, NPS, NRCAN, GeoBase, Kadaster NL, Ordnance Survey, Esri Japan, METI, Esri China (Hong Kong), and the GIS User Community'

  // var NASAGIBS_ViirsEarthAtNight2012 = L.tileLayer('https://map1.vis.earthdata.nasa.gov/wmts-webmerc/VIIRS_CityLights_2012/default/{time}/{tilematrixset}{maxZoom}/{z}/{y}/{x}.{format}', {
  // 	attribution: 'Imagery provided by services from the Global Imagery Browse Services (GIBS), operated by the NASA/GSFC/Earth Science Data and Information System (<a href="https://earthdata.nasa.gov">ESDIS</a>) with funding provided by NASA/HQ.',
  // 	bounds: [[-85.0511287776, -179.999999975], [85.0511287776, 179.999999975]],
  // 	minZoom: 1,
  // 	maxZoom: 8,
  // 	format: 'jpg',
  // 	time: '',
  // 	tilematrixset: 'GoogleMapsCompatible_Level'


    }).addTo(map);

  </script>
</body>
</html>
```

#BLAH BLAH BLAH
