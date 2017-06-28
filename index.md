
<!-- .slide: data-transition="zoom" data-background="#0D1CD1" -->

# QGIS 101
With a side dish of Statistics Norway


---

<small> by Lasse Gullvåg Sætre, for</small>

<img src="https://www.jernbanedirektoratet.no/globalassets/logo/jb_logo_web.png?scale=NoTransform" style="border: none; box-shadow: none;"/>

---

## This tutorial covers

* Basic usage of QGIS
  * Importing layers
  * Joining two layers
* QGIS plugins
*  Geospatial analysis

Note:
* Basic usage of QGIS
  * Importing a Web Map Server layer
  * Importing non-spatial data (.csv file)
  * Importing a vector layer (ESRI shapefile)
* Joining two layers
  * Joining tabular data with vector shapefile
* QGIS plugins *- we'll try the Quick OSM plugin*
  * Import specific features from OpenStreetMap
* Geospatial analysis
  * Buffer
  * Count features in polygon

---

First things first

## [Download QGIS](http://qgis.org/en/site/)

---

## Not so short, but sweet... (1/2)

You'll be familiar with QGIS, the leading Free and Open Source Software (FLOSS) Geographic Information System (GIS) application.

The guide covers importing and working on several kinds of data, and join data that isn't georeferenced with data that is.


---

## Not so short, but sweet... (2/2)

Through plugins, you are able to access the continuously expanding information in the OpenStreetMap database.

You will also have learned how to make use of SSB Grid, not just as a static image to look at, but as data to count, manipulate and play with.

---

## Install and open QGIS

* Double click installer and jam next in Windows
* Install from repository in Linux
* Drag to application folder in Mac OSX

**Open QGIS Desktop**

(we will not use QGIS Browser here)

---

![QGIS](https://i.imgur.com/zFboISk.png)

---

<!-- .slide: data-transition="zoom" data-background="#0D1CD1" -->

Part I:

# Begone blank map

---

## Add some WFS layers (1/2)

<img src="https://i.imgur.com/qUFCAXU.png" /> <!-- .element height="90%" width="90%" -->


---

## Add some WFS layers (2/2)

Kartverket Gråtone WFS:

**http://wms.geonorge.no/skwms1/wms.topo2.graatone?request=GetCapabilities&service=WMS**

<small>Choose Norwegian standard projection: WGS 84 / UTM Zone 33 (EPSG 32633)</small>

SSB:

http://ogc.ssb.no/wms.ashx?service=wms&request=getcapabilities

<small>Whichever layer, but I recommend 5km grid for performance. This tutorial goes on with population data. EPSG 32633 should be the projection.</small>


---

## Rejoice

You now posses the ability to display large amounts of data through Web Map Servers (WMS). Norwegian data can be found here:

**https://www.geonorge.no/**

---

## Despair
No way to style, manipulate, or anything.

---

<!-- .slide: data-transition="zoom" data-background="#0D1CD1" -->
Part II:
# Drawing in the data

---

Where we visit

<img src="https://www.ssb.no/_public/skins/advanced/ssb.no/images/SSB_logo_fb.png" style="border: none; box-shadow: none;" />

---

Theory:

### Grid shape

### Tabular data

---

## Just join them
<img src="https://fashionablygeek.com/wp-content/uploads/2010/08/keytar-platypus-590x382.jpg" style="border: none; box-shadow: none;" />

---

![Nojoin](https://38.media.tumblr.com/63b19d2fa98932419fb6553a1dfd0b1f/tumblr_mk981oqrW51s8spqco1_500.gif) <!-- .element height="80%" width="80%" -->

---

## Data links:

Grid shape (SSBgrid):

https://www.ssb.no/natur-og-miljo/_attachment/101145?_ts=13d3e62d7d0



Tabular data (SSB population 2017):

https://folk.uio.no/lassegsa/r250m_web_2017_m.zip

---

## Add to QGIS and join

![Join](https://i.imgur.com/PdND2BP.png) <!-- .element height="90%" width="90%" -->

---

## Style the layer

![Style](https://i.imgur.com/BwoSM2N.png) <!-- .element height="90%" width="90%" -->

---

## Congratulations

You have imported a vector layer, performed a join with a tabular dataset and styled it.

See Statistics Norway for more tabular datasets:

https://www.ssb.no/natur-og-miljo/geodata

---

<!-- .slide: data-transition="zoom" data-background="#0D1CD1" -->

Part III:
# Plugins

---

<section data-background-iframe="https://minorua.github.io/qgis/plugins/qgis2threejs/examples/forest_basin/slope.html" data-background-interactive>

</section>

---

We are going to hook into OpenStreetMap with "QuickOSM"

---

![Pluginstall](https://i.imgur.com/NaVmFsJ.png) <!-- .element height="90%" width="90%" -->

---

![QuickOSM](https://i.imgur.com/I7PYFFj.png) <!-- .element height="90%" width="90%" -->

---

## Vast amounts of data

---

<!-- .slide: data-transition="zoom" data-background="#0D1CD1" -->

Part IV:
# Geospatial analysis

---

* Select a station
* Create new layer of selection with only one station
* Create buffer around station
* Intersect with Statistics Norway population
* Count population inside Buffer

---

Select station and save layer as (UTM z33)

![savelayer](https://i.imgur.com/5f0SFNl.png) <!-- .element height="90%" width="90%" -->

---

Create buffer

![buffer](https://i.imgur.com/1kQJlzs.png) <!-- .element height="90%" width="90%" -->

---

Intersect

![Intersect](https://i.imgur.com/h2Ok4Yd.png) <!-- .element height="90%" width="90%" -->

---

"r250m_web_2017_pop_tot" * ($area / 62500)
![wrongnr](https://i.imgur.com/u8z4bos.png)


---

![Calculate](https://i.imgur.com/krfKpY8.png) <!-- .element height="90%" width="90%" -->

---

Summing up

![sum](https://i.imgur.com/xyOmePb.png) <!-- .element height="90%" width="90%" -->
