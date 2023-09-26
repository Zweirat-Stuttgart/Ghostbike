# Ghostbikes

In this repository we want to create a black/white image of our city, Stuttgart.  
On this map all Ghostbikes should be visible.

## Preparation

### Overpass Creation

With the [Overpass Turbo](https://overpass-turbo.eu/) website just execute this search to get your city and all the districts:

```
[out:json][timeout:900];
// get a few areas into .myArea
// you can add or remove an area by simply adding or removing
// one line here. 

(
{{geocodeArea:"Stuttgart"}};
{{geocodeArea:"Stuttgart-West"}};
{{geocodeArea:"Stuttgart-Mitte"}};
{{geocodeArea:"Stuttgart-Süd"}};
{{geocodeArea:"Stuttgart-Ost"}};
{{geocodeArea:"Stuttgart-Nord"}};
{{geocodeArea:"Bad Cannstatt"}};
{{geocodeArea:"Stuttgart-Birkach"}};
{{geocodeArea:"Stuttgart-Botnang"}};
{{geocodeArea:"Stuttgart-Degerloch"}};
{{geocodeArea:"Stuttgart-Feuerbach"}};
{{geocodeArea:"Stuttgart-Hedelfingen"}};
{{geocodeArea:"Stuttgart-Möhringen"}};
{{geocodeArea:"Stuttgart-Mühlhausen"}};
{{geocodeArea:"Stuttgart-Münster"}};
{{geocodeArea:"Stuttgart-S-Obertürkheim"}};
{{geocodeArea:"Stuttgart-Plieningen"}};
{{geocodeArea:"Stuttgart-Sillenbuch"}};
{{geocodeArea:"Stuttgart-Stammheim"}};
{{geocodeArea:"Stuttgart-Untertürkheim"}};
{{geocodeArea:"Stuttgart-Vaihingen"}};
{{geocodeArea:"Stuttgart-Wangen"}};
{{geocodeArea:"Stuttgart-Weilimdorf"}};
{{geocodeArea:"Stuttgart-Zuffenhausen"}};
)->.myArea;
 
// display .myArea This can be replaced by any query
// on the objects in .myArea

rel(pivot.myArea);

// print results
out geom;

{{style:
  node{opacity:0;fill-opacity:0}
}}
```

### Overpass Export

If you're satisfied with your query, just use the Export button in the top left of the Overpass Turbo website and save it as geojson.

### GPS Visualizer

You can upload this geojson now to the [GPS Visualizer](https://www.gpsvisualizer.com/map_input?form=svg) and download the according svg file.

### Manual work

Depending on how perfect you like to have it, you can now open this svg file in any vector editing program, like [InkScape](https://inkscape.org/). I removed all "double" lines and changed:   
For all districts a greyish, dashed line: `stroke:#cccccc;stroke-width:1;stroke-dasharray:2, 10`  
For the outer border a slightly thicker, white line: `stroke:#ffffff;stroke-width:3`

### Add to index

Now you can take the complete content of this modified svg file and add it to your index.html file. That's it, you have a map of your city.
