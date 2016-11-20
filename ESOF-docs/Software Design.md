![FEUP image](https://sigarra.up.pt/feup/pt/WEB_GESSI_DOCS.download_file?p_name=F-370784536/logo_cores_oficiais.jpg)

#Assignment 3: Software Design

##Introduction

This assignment covers the software architecture side, the 4+1 architectural view model and the architectural patterns that Leaflet uses. **Software architecture** is the fundamental organization of a system, embodied in its components, their relationships to each other and the environment, and the principles governing its design and evolution. In other words, it summarizes all the important decisions about the organization of the system.

The **4+1 Architectural view model** is a set of views composed of:
*   Logical view
*   Development view
*   Deployment view
*   Process view

![4+1 View Model](https://raw.githubusercontent.com/DiogoMCampos/Leaflet/ESOF-Documentation/ESOF-docs/resources/4%2B1architechture.png)

These diagrams represent different approaches to the organization and behavior of the software system.

The definition of a pattern is a means of representing, sharing and reusing knowledge. **Architectural pattern**(or architectural style) following that line of thought, is a stylized description of good architectural design practice, which has been tried and tested in different environments.
Leaflet follows the **model view controller architecture**. It separates the handling of mouse interaction from geometry that is shown on the map and others.
Another architectural pattern this project follows is **Repository architecture**. This allows changes to be propagated easily between all components. This pattern is vital for the working model used in Leaflet which allows developers to manipulate a copy of the program so as to implement a feature or correcting a issue.
**Client Server architecture** is also a architectural pattern followed by Leaflet. The program, in the begging, sends a request to popular websites to get map data.
Lastly, **Layered architecture** is also implemented. Leaflet has a map class which uses all the elements in the layer below it.


##Logical View

The logical view displays a package diagram. It represents the connections between each package and shows how the source code is organized.

![Package diagram](https://raw.githubusercontent.com/DiogoMCampos/Leaflet/ESOF-Documentation/ESOF-docs/resources/Package%20Diagram.png)

*   **map**: main package that utilizes all others;
*   **control**: contains classes that handle map controls. All classes are derived from one single file;
*   **dom**: implements the usage of dom related events;
*   **core**: enables all the instances necessary to the operation of the program;
*   **handler**:allows for interaction between the user and the program by means of events;
*   **geometry**: set of geometrical forms to display on top of the map;
*   **layer**: represents panels to be added on top of the map;
*   **marker**: optional layer which contains elements to be displayed on a layer;
*   **vector**: optional layer that implements geometrical figures;
*   **tile**: instantiates the bitmap graphics in a grid arrangement in order to display the map;

##Development View

Describes how the program is composed and the dependencies and relations between the different modules.

![Component View](https://raw.githubusercontent.com/DiogoMCampos/Leaflet/ESOF-Documentation/ESOF-docs/resources/Component%20View.png)

The **map** module, which is the main one, is responsible for the creation of the map and uses every other component to build the final visualization. Every other module has a specific purpose, although some of them share similar goals and can be grouped together.

*   The **control** and **handler** modules are responsible for user interaction and how the map reacts to events.
*   The **geometry**, **layer**, **marker**, **vector** and **tile** modules are responsible for the visualization, handling the display of tiles, markers, pop-ups or any other elements.

This separation in different modules allows Leaflet contributors and plugin makers to easily understand the code base and make changes concerning specific aspects of the library without having to modify the other modules.

##Deployment View

Depiction of the hardware nodes and relations between them.

![Deployment View](https://raw.githubusercontent.com/DiogoMCampos/Leaflet/ESOF-Documentation/ESOF-docs/resources/Deployment%20View.png)

Although the actual processing and event handling occur only in the client machine, both Leaflet and the map using it have to be loaded. Frequently, the map is embedded in a web page and this is done by a request to a server, which hosts the page. Seeing that all scripting is client-side, this server can be a simple storage server (for instance, a *S3 bucket*).

Since Leaflet is a library that is used in many web pages, its deployment is often made through a CDN, although it is also possible to include it in the server hosting the page.

##Process View

The process view shows how the system handles run-time interacting processes.

![Process View](https://raw.githubusercontent.com/DiogoMCampos/Leaflet/ESOF-Documentation/ESOF-docs/resources/Activity%20Diagram.png)
As shown in the diagram, when Leaflet is started the map is loaded. The map loading consists in getting data from the map provider (for example, from OpenStreetMap) and displaying the map according to the settings.
When the user interacts with the map, Leaflet will handle the event and display the information requested by the event. For instance, if the user drags the map, the show area will be different.
