![FEUP image](https://sigarra.up.pt/feup/pt/WEB_GESSI_DOCS.download_file?p_name=F-370784536/logo_cores_oficiais.jpg)

#Assignment 2: Requirements Elicitation

##Introduction
Leaflet is a JavaScript open-source library for mobile-friendly interactive maps.
This assignment will focus on how the project deals with requirement elicitation.

##Requirements
A requirement is a feature that is formulated through a study across the User's intentions.

Leaflet new features can be chosen in two ways: either the main core team can decide which features to implement or the community.

###Functional and Non Functional Requirements
System Requirements can be separated in two parts, Functional and Non Functional. Functional Requirements are requirements for the application to run, the Non Functional Requirements are requirements to improve the application performance.

There are some examples in Leaflet.

####Functional Requirements
*   A variety of maps

####Non Functional Requirements  
*   Is an Open Source project
*   The project is documentated
*   The program tries to be efficient

###Elicitation
The team usually works on fixing the existing bugs or implementing some new features (as we have previously mentioned, right now the team is working on map rotation).

However, if a user has an idea of a new feature he can suggest it  [here](https://leaflet.uservoice.com/forums/150880-ideas-and-suggestions-for-leaflet). Users can also up-vote the listed features and the team will discuss the implementation of this feature. If the team decides the suggestion is good, they mark it as "planned" and will implement it later.

Users can also use Gitter to chat with the contributors and have a more personal opinion about the request made.

###Analysis and Negotiation
Through the discussions at the forum or at the chat it's possible to know whether the feature is good or what is missing.

After the implementation of the feature the contributor can make a Pull Request and after a new analysis the Pull Request can be accepted.

###Specification
The Documentation specifies all of the project and can be consulted [here](http://leafletjs.com/reference.html).

###Validation
All of the project has to be submitted to a variety of tests. The program is tested personally and automatically using unit tests. But all of these tests are not sufficient so they have a forum for the users to report all of the bugs to be corrected.

##Use Cases

##Domain Model
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
