![FEUP image](https://sigarra.up.pt/feup/pt/WEB_GESSI_DOCS.download_file?p_name=F-370784536/logo_cores_oficiais.jpg)

#Assignment 5: Software Maintenance/Evolution

##Software Evolution and Maintainability
As errors appear, new features are requested or performance needs to be improved, software systems need to evolve. This proves costly to many organizations, as many man-hours can be needed to perform the needed changes.

Leaflet, as an open-source project, benefits from the support of the community to both identify these changes and implement them, which may help reduce this cost. On the other hand, having the input of so many different users and developers requires the core team to keep the code quality up and the software maintainable.

##Better Code Hub
In order to evaluate Software Maintainability, i used the Better Code Hub service and this were the results:
![Results](https://raw.githubusercontent.com/DiogoMCampos/Leaflet/ESOF-Documentation/ESOF-docs/resources/BCH%20Results.png)
This service analyses the repository on 10 different parameters, although for some projects some of the properties are not evaluated properly.  

###Automate Tests
Better Code Hub only checks tests for Java and C# currently, which leads to Leaflet failing this section due to being a JavaScript project.

Manually, we checked the number of lines and asserts (*expect*) in four random test files and compared them to the number of lines in their source code equivalent (including comments) following the criteria used by Better Code Hub.

According to BetterCodeHub, Leaflet has 7352 lines of code, so as a medium system, the number of lines of test code should be **50%** of the number of lines of source code and the assert density should be at least **1%**.

####TileLayer:
*   */src/layer/tile/TileLayer.js*: 281 lines.
*   */spec/suites/layer/tile/TileLayerSpec.js*: 470 lines and 32 expect.
*   Percentage of test code lines: 167%.
*   Assert Density: 6.8%

####Events:
*   */src/core/Events.js*: 289 lines.
*   */spec/suites/core/EventsSpec.js*: 607 lines and 96 expect.
*   Pertentage of code lines: 241%
*   Assert Density: 15.8%

####Bounds:
*   */src/geometry/Bounds.js*: 155 lines.
*   */spec/suites/geometry/BoundsSpec.js*: 87 lines and 20 expect.
*   Percentage of test code lines: 56.1%
*   Assert Density: 23%

####LatLng:
*   */src/geo/LatLng.js*: 129 lines.
*   */spec/suites/geo/LatLngSpec.js*: 140 lines and 32 expect.
*   Percentage of test code lines: 108.5%
*   Assert Density: 22.9%

Considering this results we believe that Leaflet would pass this section if it was supported by Better Code Hub.

##Evolution Process
In this last assignment it was required to evolve a feature. Since there was a consensus in the group to further the development of the Leaflet project , an email was sent to the main team about features they would like to see implemented on Leaflet. One of the features they talked about was related to Polyline wrapping. Polylines are used to draw lines between given points on a map and they asked for an implementation of the option to wrap these coordinates. If this option is enabled and two points are separated in longitude by more than 180 degrees, these points will not cross the entire map but will take the shortest path around the map.
The starting point to implement this feature was to add the option noWrap on Polyline options. The next step was to modify the convertLatLngs method on Polyline by calling wrapCoordinates if the option noWrap was set. This method receives an array of coordinates and checks if two coordinates are separated on longitude by more than 180 degrees: if so, this method will calculate the angle between the starting point and the next point but within the same longitude range as the previous ponit. After calculating this angle, this polyline will be split into two. The first point will connect to a new point near the longitude limit (-180 degrees or 180 degrees depending on the direction) and the destination point will be connected to a point on the opposite longitude.
However, this was not enough since Polyline will draw a line between all the adjacent points. To fix this, an attribute was added to some points so it won't connect the last point to the point that was marked. After this, the projectLatLngs method was modified to separate these lines by adding different arrays called "rings" on the argument "result" instead of only one array.

##Group members
*   [Bruno Barros](https://github.com/BrunoBarros21) - up201405249@fe.up.pt
*   [Diogo Campos](https://github.com/DiogoMCampos) - d.diogocampos@gmail.com
*   [Fábio Caramelo](https://github.com/Caramelo18) - up201404783@fe.up.pt
*   [William Fukunaga](https://github.com/williamnf) - up201405119@fe.up.pt

##Contributions

|       **Names**   | **Percentage** |
|:----------------:	|:------------:	|
| Bruno Barros     	|           	|
| Diogo Campos     	|           	|
| Fabio Caramelo   	|           	|
| William Fukunaga 	|           	|
