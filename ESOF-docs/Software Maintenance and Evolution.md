![FEUP image](https://sigarra.up.pt/feup/pt/WEB_GESSI_DOCS.download_file?p_name=F-370784536/logo_cores_oficiais.jpg)

#Assignment 5: Software Maintenance/Evolution

##Software Maintainability
In order to evaluate Software Maintainability we used the Better Code Hub service and this were the results:
![Results](https://raw.githubusercontent.com/DiogoMCampos/Leaflet/ESOF-Documentation/ESOF-docs/resources/BCH%20Results.png)
This service evaluates the repository on 10 different parameters. However, sometimes Better Code Hub does not evaluate the repository propertly. For instance, on our example we consider that some components such as "Write Simple Units of Code", "Keep Architecture Components Balanced" and "Automate Tests" were not evaluated correctly.

##Evolution Process
On this last assignment it was asked to evolve a feature. Since we wanted to be helpful to the main team, we contacted them and asked them for a feature they would like to be implemented on Leaflet. One of the features they would like to see on Leaflet was related to Polyline wrapping. Polylines are used to draw lines between given points on a map and we were asked to add the option to wrap this coordinates. If this option is enabled and two points are separated in longitude by more than 180 degrees, this points will not cross the entire map but will take the shortest path around the map.
The starting point to implement this feature was to add the option noWrap on Polyline options. The next step was to modify the convertLatLngs method on Polyline by calling wrapCoordinates if the option noWrap was set. This method receives an array of coordinates and checks if two coordinates are separated on longitude by more than 180 degrees: if so, this method will calculate the angle between the starting point  (ALTERAR ISTO AQUI).
However, this was not enough since Polyline will draw a line between all the adjacent points. To fix this, an attribute was added to some points so it won't connect the last point to the point that was marked. After this, the projectLatLngs method was modified to separate this lines by adding differnt arrays called "rings" on the argument "result" instead of only one array.

##Group members
* [Bruno Barros](https://github.com/BrunoBarros21) - up201405249@fe.up.pt
* [Diogo Campos](https://github.com/DiogoMCampos) - d.diogocampos@gmail.com
* [Fábio Caramelo](https://github.com/Caramelo18) - up201404783@fe.up.pt
* [William Fukunaga](https://github.com/williamnf) - up201405119@fe.up.pt

##Contributions

|       **Names**   | **Percentage** |
|:----------------:	|:------------:	|
| Bruno Barros     	|           	|
| Diogo Campos     	|           	|
| Fabio Caramelo   	|           	|
| William Fukunaga 	|           	|
