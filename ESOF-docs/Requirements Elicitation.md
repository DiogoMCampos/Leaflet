![FEUP image](https://sigarra.up.pt/feup/pt/WEB_GESSI_DOCS.download_file?p_name=F-370784536/logo_cores_oficiais.jpg)

#Assignment 2: Requirements Elicitation

##Introduction
Leaflet is a JavaScript open-source library for mobile-friendly interactive maps.
This assignment will focus on how the project deals with requirement elicitation.

##Requirements
A requirement is a feature that solves a particular problem, and it is usually formulated through a study across the user's intentions.

This process of formulating requirements is known as requirements engineering and it consists on multiple phases. In the project we are studying, this process seems rather informal.

The Leaflet requirements are chosen in two ways:
*   The main core team decides on a feature to implement
*   The community suggests a new feature

###Functional and Nonfunctional Requirements
Requirements can be either **functional requirements**, which specify the capabilities of the application and the user problems the team aims to solve, or **nonfunctional requirements**, which describe the constraints to the solution implemented and its execution.


####Functional Requirements
*   Map visualization on a browser
*   Supporting the integration of a variety of maps, through the use of tile layers
*   Allowing the end user to interact with the map by dragging, zooming or clicking
*   Allowing developers to customize their maps easily, both in functionality and styling

####Non Functional Requirements  
*   Being an Open Source project
*   Having an extensive documentation
*   Being lightweight and supporting multiple browsers and devices (including mobile)
*   Using no external dependencies
*   Focusing on being simple and doing the basics perfectly

###Elicitation
The team usually works on fixing the existing bugs or implementing new features (as we have previously mentioned, right now one of those features is the map rotation).

This process is heavily integrated with the community, as there are two channels where both the users and developers can contribute to the elicitation:
*   By reporting bugs on the [GitHub Issues page](https://github.com/Leaflet/Leaflet/issues)
*   By suggesting a new feature or voting on the existing ones on the [Uservoice page](https://leaflet.uservoice.com/forums/150880-ideas-and-suggestions-for-leaflet)

The team, in order to decide what to work on, considers these two channels and their own ideas, taking into account Leaflet's other requirements. In practice, this means that the most impactful bugs and the most upvoted suggestions will be the focus of their work, as long as they fit the project scope and requirements.

Users can also use Gitter to chat with the contributors and have a more personal opinion about the request made.

###Analysis and Negotiation
Through the discussions at the forum or at the chat it's possible to know whether the feature is good or what is missing.

After the implementation of the feature the contributor can make a Pull Request and after a new analysis the Pull Request can be accepted.

###Specification
Although we weren't able to find a SRS document, there are multiple documents concerning software requirements and user manual available.

*   There is the API Reference that can be consulted [here](http://leafletjs.com/reference.html), which includes usage information for the Leaflet API.
*   There is a [features page](http://leafletjs.com/#features) listing the capabilities of the library.
*   The [changelog](https://github.com/Leaflet/Leaflet/blob/master/CHANGELOG.md) includes information on how the project evolved over time with each release.

###Validation
The goal of the validation process is to assure that the requirements define the desired goals. The program is tested automatically using unit tests, ensuring it satisfies the set requirements. If it passes the tests, the pull request will be considered by the main team. If it passes the tests, the pull request will be considered by the main team.
But all of these tests are not sufficient so they have a issues page for the users to report all of the bugs to be corrected.

##Use Cases

![Use case](https://raw.githubusercontent.com/DiogoMCampos/Leaflet/ESOF-Documentation/ESOF-docs/resources/UseCaseDiagram.png)


If the user is the actor we have the following use case:
*   Map visualization - the user can visualize the generated map. The user interaction with the map will depend on the configuration done by the developer.
If the developer is the actor we have the following use cases:
*   Map configuration - the developer can configure the way the user is going to visualize and interact with the map.
*   Events - the way user inputs (like clicks, drags) are handled.
*   PopUps - map popups can be displayed in several ways.
*   Control - gives the ability to alter the map or show visualization information.
*   Layer - the way the map is displayed, for example how images or streets are displayed.
*   Plugins - plugins can be included in the map to display.


##Domain Model

![Domain model](https://raw.githubusercontent.com/DiogoMCampos/Leaflet/ESOF-Documentation/ESOF-docs/resources/DomainModel.png)
*   Map - The central class of the API. It is used to create a map on a page and manipulate it.

*   Handler - Base class for handler classes that are used internally to inject interaction features like dragging to classes like Map and Marker.

*   Events - A set of methods shared between event-powered classes (like `Map` and `Marker`). Generally, events allow you to execute some function when something happens with an object (e.g. the user clicks on the map, causing the map to fire `'click'` event).

*   Geo - Abstract class that defines coordinate reference systems for projecting geographical points into pixel (screen) coordinates and back to coordinates in other units.

*   Layer - A set of methods that all Leaflet layers use. Allows for map handling, such as drawing simple geometry or dragging icons on the map

*   Geometry - Configuring shapes for drawing to the map and transforming them.

*   Control - Base class for implementing map controls. Handles positioning.

##Group members
*   [Bruno Barros](https://github.com/BrunoBarros21) - up201405249@fe.up.pt
*   [Diogo Campos](https://github.com/DiogoMCampos) - d.diogocampos@gmail.com
*   [Fábio Caramelo](https://github.com/Caramelo18) - up201404783@fe.up.pt
*   [William Fukunaga](https://github.com/williamnf) - up201405119@fe.up.pt

##Contributions

|       **Names**   | **Percentage** |
|:----------------:	|:------------:	|
| Bruno Barros     	|      25%     	|
| Diogo Campos     	|      25%     	|
| Fabio Caramelo   	|      25%     	|
| William Fukunaga 	|      25%     	|
