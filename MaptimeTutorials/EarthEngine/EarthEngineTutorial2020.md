![Google Earth Engine Logo](imagesEngine/earth-engine-logo_sm.png)
# Introduction to Google Earth Engine

## What is Google Earth Engine?

We're all fairly familiar with Google Earth: Flying around 2D and 3D renderings of the globe to explore information and imagery of our planet. You can add KML data to it and create projects of discovery. Pretty good stuff.

This is Google Earth:

![Google Earth G U I](imagesEngine/GoogleEarthSnapshot.JPG)

But this is Google Earth ENGINE:

![Google Earth Engine G U I](imagesEngine/GoogleEarthEngineSnapshot.JPG)

It's a planetary-scale platform for doing data science. Google Earth Engine allows users to run algorithms on georeferenced imagery and vectors stored on Google's infrastructure. Instead of being just an observer, you have the ability to conduct spatial analysis on the global datasets found in Earth Engine's data catalog. You can also load your own data for your projects, or even submit a request a particular dataset you'd like Earth Engine to host.

What's on offer:

![data computation A P I applications graphic](imagesEngine/EngineOfferings.JPG)

You have to apply to have one (and only one) Google account approved for access. Do read the [Terms of Service](https://earthengine.google.com/terms/) carefully.

NOTE: *This tutorial is in the context of nonprofit, research, and education use. Commercial applications of Google Earth Engine require a paid commercial license.*

A good place for more orientation: https://earthengine.google.com/faq/

And once you sign up, you'll have access to the code editor shown above where you can follow along with the excellent [Javascript Starting Guide](https://developers.google.com/earth-engine/guides/getstarted). (Python installs are an option as well, but the guide examples are mainly Javascript.) 

## The Earth Engine Data Catalog

https://developers.google.com/earth-engine/datasets

## Data

### Types

Image

Vector

Load your own!
- Shapefiles
- CSVs (lat/lon columns, or spatial geometry column such as geoJSON)

### Satellites

## The Code Editor

Use your registered Google account to access the code editor here:
https://code.earthengine.google.com/


*CENTER panel*
- Javascript code editor

*LEFT panel*
- Code examples
- Your saved scripts
- Searchable API reference
- Asset manager for private data

*RIGHT panel* 
- Inspector for querying the map (gives info about the layers)
- Output console
- Manager for long-running tasks

*BOTTOM panel*
- Map Output! (Base map plus layers added from script)


## Getting Started

## Javascript

## Examples

### Loading a Satellite Image

```
// Load the image from the archive.
var image = ee.Image('LANDSAT/LC08/C01/T1/LC08_044034_20140318');

// Define visualization parameters in an object literal.
var vizParams = {bands: ['B5', 'B4', 'B3'], min: 5000, max: 15000, gamma: 1.3};

// Center the map on the image and display.
Map.centerObject(image, 9);
Map.addLayer(image, vizParams, 'Landsat 8 false color');

```

### Colorado Elevation

```
// Plot a histogram of elevation in Colorado.

var elevation = ee.Image('CGIAR/SRTM90_V4');
var colorado = ee.Geometry.Rectangle({
  coords: [-109.05, 37, -102.05, 41],
  geodesic: false
});

// Generate the histogram data.  Use minBucketWidth for nice sized buckets.
var histogram = ui.Chart.image.histogram({
  image: elevation,
  region: colorado,
  scale: 200,
  minBucketWidth: 300
});
histogram.setOptions({
  title: 'Histogram of Elevation in Colorado (meters)'
});

print(histogram);

Map.addLayer(elevation.clip(colorado));
Map.setCenter(-107, 39, 6);

```

### Urban Areas Impervious Surface Growth (does it ever shrink?)
