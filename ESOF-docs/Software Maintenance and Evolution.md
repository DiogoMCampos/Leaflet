![FEUP image](https://sigarra.up.pt/feup/pt/WEB_GESSI_DOCS.download_file?p_name=F-370784536/logo_cores_oficiais.jpg)

 [![BCH compliance](https://bettercodehub.com/edge/badge/DiogoMCampos/Leaflet)](https://bettercodehub.com)
#Assignment 5: Software Maintenance/Evolution

##Software Evolution and Maintainability
As errors appear, new features are requested or performance requires improvement, software systems need to evolve. This proves costly to many organizations, as many man-hours can be needed to perform the necessary changes.

Leaflet, as an open-source project, benefits from the support of the community to both identify these changes and implement them, which may help reduce this cost. On the other hand, having the input of so many different users and developers requires the core team to keep the code quality up and the software maintainable.

##Better Code Hub
Software Improvement Group (SIG for short) provided a source code analysis tool named Better Code Hub (BCH for short) in order to evaluate Software Maintainability and these were the results of its service:
![Results](https://raw.githubusercontent.com/DiogoMCampos/Leaflet/ESOF-Documentation/ESOF-docs/resources/BCH%20Results.png)
This service analyses the repository on 10 different parameters, although for some projects some of the properties are not evaluated properly.  

###Automate Tests
![Automate Tests](https://raw.githubusercontent.com/DiogoMCampos/Leaflet/ESOF-Documentation/ESOF-docs/resources/9.AutomateTests.png)
Better Code Hub only checks tests for Java and C# currently, which leads to Leaflet failing this section due to being a JavaScript project.

Manually, the group checked the number of lines and asserts (*expect*) in four random test files and compared them to the number of lines in their source code equivalent (including comments) following the criteria used by Better Code Hub.

According to Better Code Hub, Leaflet has 7352 lines of code, so as a medium system, the number of lines of test code should be **50%** of the number of lines of source code and the assert density should be at least **1%**.

####TileLayer:
*   */src/layer/tile/TileLayer.js*: 281 lines.
*   */spec/suites/layer/tile/TileLayerSpec.js*: 470 lines and 32 expect.
*   Percentage of test code lines: 167%.
*   Assert Density: 6.8%

####Events:
*   */src/core/Events.js*: 289 lines.
*   */spec/suites/core/EventsSpec.js*: 607 lines and 96 expect.
*   Percentage of code lines: 241%
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

Considering these results we believe that Leaflet would pass this section if it was supported by Better Code Hub.

NOTE: This analysis was made in the early phase of the assignment. During that time, Better Code Hub released a new version and we decided to try to include the tests again. However, this service was unavailable and therefore wasn't possible to make full use of this updated version. We consider that the

###Simple Units of Code
![Simple Units of Code](https://github.com/DiogoMCampos/Leaflet/blob/ESOF-Documentation/ESOF-docs/resources/2.%20SimpleUnits.png?raw=true)
In this topic, Better Code Hub verifies the existence of branch points (if, for, while, etc.).
Leaflet fails this because of an excessive use of these conditionals and loops.

Leaflet is a highly customizable project. Therefore, it is necessary to be abundant in the use of conditionals to handle the activation or deactivation of each feature.
As for loops, Leaflet uses them mostly to display additional layers provided by the user.

As for the other test cases, Leaflet passed every test successfully.
With all of the tests Better Code Hub provides, it's possible to see Leaflet has a clean, small and structured code with no repetitions of the same. Leaflet also doesn't have too many arguments in their methods which makes it easy to understand.

To conclude, it's possible to say Leaflet is a well organized and efficient open source project.

##Evolution Process

*"Leaflet doesn't try to do everything for everyone. Instead it focuses on making the basic things work perfectly."*

In order to make maintaining the project easier, Leaflet focuses on a specific set of features and enforces this rather strictly. There are some clear paths to how new features are chosen, which have been discussed in the previous reports.

Since there was a consensus in the group to further the development of the Leaflet project, an email was sent to the main team about features they would like to see implemented on Leaflet. One of the features they talked about was related to Polyline wrapping around the International Date Line as we were already familiar with the topic, due to having worked on it in the last assignment.

Polylines are used to draw lines between given points on a map and there was an issue ([2645](https://github.com/Leaflet/Leaflet/issues/2645)) regarding the wrapping of the coordinates around the antimeridian. The goal was to implement an option to wrap these coordinates. If this option is enabled and two points are separated in longitude by more than 180 degrees, these points will not cross the entire map by means of drawing the direct path which is longer, it will generate a shorter path around the antimeridian. If the option is disabled, the current behavior will stand.

The starting point to implement this feature was to add the option noWrap on Polyline options. The next step was to modify the convertLatLngs method on Polyline by calling wrapCoordinates if the option noWrap was set. This method receives an array of coordinates and checks if two coordinates are separated on longitude by more than 180 degrees: if so, this method will calculate the angle between the starting point and the next point but within the same longitude range as the previous point. After calculating this angle, this polyline will be split into two. The first point will connect to a new point near the longitude limit (-180 or 180 degrees depending on the direction) and the destination point will be connected to a point on the opposite longitude.

However, this was not enough since Polyline will draw a line between all the adjacent points. To fix this, an attribute was added to some points so it won't connect the last point to the point that was marked. After this, the projectLatLngs method was modified to separate these lines by adding different arrays called "rings" on the argument "result" instead of only one array.

We submitted a Pull Request ([5206](https://github.com/Leaflet/Leaflet/pull/5206)) which contains an implementation of the specified feature. There are hardcoded values in our implementation that we intend to replace, but we weren't sure about some issues related to the longitude range not being that of the Earth. We did ask for feedback via e-mail some days before the deadline.

##Group members
*   [Bruno Barros](https://github.com/BrunoBarros21) - up201405249@fe.up.pt
*   [Diogo Campos](https://github.com/DiogoMCampos) - d.diogocampos@gmail.com
*   [Fábio Caramelo](https://github.com/Caramelo18) - up201404783@fe.up.pt
*   [William Fukunaga](https://github.com/williamnf) - up201405119@fe.up.pt

##Contributions

|       **Names**   | **Percentage** |
|:----------------:	|:------------:	|
| Bruno Barros     	|       25%    	|
| Diogo Campos     	|       25%    	|
| Fabio Caramelo   	|       25%    	|
| William Fukunaga 	|       25%    	|
