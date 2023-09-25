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
