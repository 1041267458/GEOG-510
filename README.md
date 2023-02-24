# GEOG-510
GEOG 510 Course website

## About Me
* Hi there 👋
* I'm Yinan 😄
* I'm a GIS and Data Science lover and begainer ⚡
* I'm currently learning Python and Google Earth Engine 🌱
* Feel free to contact me through [email](mailto:feng.945@osu.edu) 📫
* You can find more infomation about me on my [personal webpage](https://u.osu.edu/feng.945/) 💬

## GRACE Satellite Data
Gravity Recovery and Climate Experiment project, launched on 17 March 2002 by NASA and German Aerospace Center (see project webiste [here](https://grace.jpl.nasa.gov/mission/grace/)), is able to measure the changes of Earth’s gravity field (Adam, 2002). Scientists are subsequently capable of interpreting these changes in gravity as water movement, whether on the surface or under the ground.

GRACE Tellus Monthly Mass Grids provides monthly gravitational anomalies relative to a 2004-2010 time-mean baseline. The data contained in this dataset are units of "Equivalent Water Thickness" which represent the deviations of mass in terms of vertical extent of water in centimeters. See the provider's Monthly Mass Grids Overview for more details.

The GRACE Tellus (GRCTellus) Monthly Mass Grids dataset is produced by three centers: CSR (U. Texas / Center for Space Research), GFZ (GeoForschungsZentrum Potsdam), and JPL (NASA Jet Propulsion Laboratory). Each center is a part of the GRACE Ground System and generates Level-2 data (spherical harmonic fields) used in this dataset. The output includes spherical harmonic coefficients of the gravity field and of the dealiasing fields used to compute them. Since each center independently produces the coefficients, the results may be slightly different. It is recommended for most users to use the mean of all three datasets. 

![GRACE CSR SS RL05][sample]

[sample]:https://www2.csr.utexas.edu/grace/gravity/ggm05/ggm05-01.png
Source: https://www2.csr.utexas.edu/grace/gravity/

Also, here is a Youtube Video about GRACE Project

<a href="http://www.youtube.com/watch?feature=player_embedded&v=MaxBOvQ2a_o" target="_blank"><img src="http://img.youtube.com/vi/MaxBOvQ2a_o/0.jpg" 
alt="For 15 Years, GRACE Tracked Freshwater Movements Around the World" width="240" height="180" border="10" /></a>

For 15 Years, GRACE Tracked Freshwater Movements Around the World
## Google Earth Engine Coding Sample
1. Read and load the data
```javascript
// Load the GRACE data
var grace_data = ee.ImageCollection("NASA/GRACE/MASS_GRIDS/LAND");
print('GRACE',grace_data)

```
2. Visualize the data
```javascript
// Visualize a GRACE data example
var grace_example = grace_data.first()
var graceViz = {bands: ['lwe_thickness_csr'],min: -20.0, max: 20.0, palette: ['red','blue']};

Map.centerObject(grace_example,2); //
Map.addLayer(grace_example,graceViz,''Equivalent Water Thickness CSR'');

```
