![FEUP image](https://sigarra.up.pt/feup/pt/WEB_GESSI_DOCS.download_file?p_name=F-370784536/logo_cores_oficiais.jpg)

#Assignment 3: Software Design

##Introduction

Leaflet follows the model view controller architecture. It separates the handling of mouse interaction from geometry that is shown on the map and others.
One architectural pattern this project follows is **Repository architecture**. This allows changes to be propagated easily between all components.
Another pattern is **Client Server architecture**. The program sends a request to popular websites to get map data.

##Logical View
The logical view displays a package diagram. It represents the connections between each package and shows how the source code is organized.
![Package diagram](https://raw.githubusercontent.com/DiogoMCampos/Leaflet/ESOF-Documentation/ESOF-docs/resources/Package%20Diagram.png)

*   **map**: main package that utilizes all others;
*   **control**: contains classes that handle map controls. All classes are derived from one single file;
*   **dom**: implements the usage of dom related events;
*   **core**: provides
*   **handler**:allows for interaction between the user and the program by means of events;
*   **geometry**: set of geometrical forms to display on top of the map;
*   **layer**: represents panels to be added on top of the map;
*   **marker**: optional layer which contains elements to be displayed on a layer;
*   **vector**: optional layer that implements geometrical figures;
*   **tile**: optional layer which allows the user to put a panel in top of the map;

##Development View
Shows how the program is composed.
![Component View](https://raw.githubusercontent.com/DiogoMCampos/Leaflet/ESOF-Documentation/ESOF-docs/resources/Component%20View.png)

##Deployment View

##Process View
The process view shows how the system handles run-time interacting processes.
![Process View](https://raw.githubusercontent.com/DiogoMCampos/Leaflet/ESOF-Documentation/ESOF-docs/resources/Activity%20Diagram.png)
As shown in the diagram, when Leaflet is started the map is loaded. The map loading consists in getting data from the map (for example, from Open Street Maps) and displaying the map according to the settings.
When the user interacts with the map, Leaflet will handle the event and display the information requested by the event. For instance, if the user drags the map, the show area will be different.
