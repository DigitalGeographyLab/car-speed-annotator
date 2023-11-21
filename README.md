# Realistic car speeds for the Helsinki metropolitan region

This is a Python package to ‘bake in’ car speeds into the edges of an
OpenStreetMap dump, according to data looked up from a floating car data set,
using the methods described in [Perola
(2023)](http://hdl.handle.net/10138/358181). The data contained in this package
covers the Helsinki metropolitan area.

This package is used, for instance, for [calculating travel time matrices of the
metropolitan
area](https://github.com/DigitalGeographyLab/Helsinki-Travel-Time-Matrices).


## Use

Instantiate a `CarSpeedAnnotator()` using one of `rush-hour`, `midday` or `nighttime` to account for the different driving speeds at different congestion levels. Then, call its `annotate()` method with an input and an output file (both either `pathlib.Path`s or `str`).

```
>>> from car_speed_annotator import CarSpeedAnnotator
>>> car_speed_annotator = CarSpeedAnnotator("rush-hour")
>>> car_speed_annotator.annotate("input.osm.pbf", "output.osm.pbf")
```


## Dependencies

This package calls [`osmium`](https://docs.osmcode.org/pyosmium/latest/ref_osmium.html), which is available as a package for most Linux distributions (e.g., `osmium-tool` on Ubuntu and Arch).
