# Mobile-OGC-Client

## Tutorial/Hackathon for the VESPA/PLANMAP Meeting Paris, 1-3 July 2019

### Possible Tasks for participation

- Conceptual, e.g. which data to display
  - Basemaps (WMS)
  - Footprints (WFS), etc... 
  As concrete as possible, e.g. ODE footprints, Hirise Basemap, collection of WMS/WFS links

- Brainstorming for features, e.g. only data viz, 3D, mapping app, mobile GIS, measuring, editing, queries ... ?

- Low-level technical issues, e.g. WGS84 vs. planetary SRS, projected/unprojected, e.g. how to address poles, mapping over dateline?
  How large are the offsets if you overlay data with different radii definitions, e.g. MOLA/IAU2000 on Mars?
  Radius 3396190 vs. 3396000 (VESPA Crism, HRSC)

- Interface design

**Boil down to absolute minimum!**

- Native App (Java/Swift/Onjective-C) or Javascript or ???

- If Javascript:
  - just bookmark or app (e.g. Cordova)?
  - Which libary/framework? Cesium, OpenLayers, [ol-cesium](https://openlayers.org/ol-cesium/), leaflet
  - Controls: ol-layerswitcher (pure/DIV)

- [Cordova](./cordova-howto.md)
