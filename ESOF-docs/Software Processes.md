![FEUP image](https://sigarra.up.pt/feup/pt/WEB_GESSI_DOCS.download_file?p_name=F-370784536/logo_cores_oficiais.jpg)

#Assignment 1: Software Processes

![Leaflet image](https://rawgit.com/Leaflet/Leaflet/master/src/images/logo.svg)

##Project description
Leaflet is an open-source library for mobile-friendly interactive maps. It is designed to be very lightweight, in order to have a great performance across multiple platforms, and highly extensible, allowing user-created plugins.

Although Leaflet uses recent technologies such as HTML5 and CSS3, it is also accessible on older browsers, due to continued efforts on maintaining compatibility.

The first commit to GitHub was on September 1st, 2010 and the version 1.0 was released on September 26, 2016. Over the past 6 years, Leaflet has had 100 different contributors (28 in 2016 alone), with Vladimir ([mourner](https://github.com/mourner)), Ivan ([IvanSanchez](https://github.com/IvanSanchez)), Yohan ([yohanboniface](https://github.com/yohanboniface)) and Per ([perliedman](https://github.com/perliedman)) being the core ones.

The software is published under the [2-clause BSD License](https://github.com/Leaflet/Leaflet/blob/master/LICENSE).

##Software development Process

###Project development
Leaflet doesn't have proper teams, they have a small team and everyone can work on every area of development, although each core member specializes in one or more topics.

Since the time spent by the contributors on the project is small, they don't use software development processes like Agile or XP, focusing on solving issues as they are reported. The issues published are usually filtered because sometimes the reported issue isn't a bug but a user problem. Leaflet has no release dates.

Despite not following a strict software development process, it is necessary to include test in every Pull Request, for validation purposes. It is also important that someone else reviews that request before merging with the master branch.

Leaflet isn't very big which facilitates understanding the code and allows diversity in terms of plugins.

The current Leaflet version is a stable version (1.0) and the idea for the future is to focus on frequent and small releases ([see 1.0 blog post here](http://leafletjs.com/2016/09/27/leaflet-1.0-final.html)), maintaining support for the current features while also implementing new ones, such as map rotation and support for ES6 modules.

###Repository structure
According to the core members of this project, they use a branch separate from the master branch to work on additional features and/or fix bugs. More specifically, they use a single branch per feature or bug.

The repository is divided in multiple folders: 'src' for source files, the 'doc' folder is for the documentation, tests are included in the 'spec' folder while the 'debug' folder contains pages with various features used for debugging.

###Activity
The project is active, with 54 commits to the master branch in the past month (as of October 16, 2016) and 35 merged Pull Requests. In average they have at least one commit per day.

Nowadays there are more than 200 opened issues, labeled according to the type. Some of them are simple issues (labeled as easy fix, to be more accurate) which might be good starting points for us to participate in the project later.

###Opinions
Since the group in charge of this project is very small, it's very hard to provide support for every plugin developed by other people and some of them are not actively maintained. Despite that, the team hopes to be able to achieve a stable plugin environment and work more closely with some of the plugin developers, now that they have achieved the 1.0 release.

Seeing that Leaflet doesn't have release dates, theoretically the members don't feel pressured to provide the software in time of the release. Therefore, it is more likely for them to provide software versions that don't have a lot of bugs.

It is possible that other people not directly involved in the project can make some plugins. And since the main core is kept simple it makes contributing easier and allows the focus to be on the important issues. However, this brings some disadvantages, as plugins have a varying amount of support and some of them are outdated.

The members meet in a chat room in Gitter, which is an instant messsaging system for developers and users of GitHub.

##Oficial project page
http://leafletjs.com/

##Group members
* [Bruno Barros](https://github.com/BrunoBarros21) - up201405249@fe.up.pt
* [Diogo Campos](https://github.com/DiogoMCampos) - d.diogocampos@gmail.com
* [Fábio Caramelo](https://github.com/Caramelo18) - up201404783@fe.up.pt
* [William Fukunaga](https://github.com/williamnf) - up201405119@fe.up.pt

##Contributions

|       **Names**   | **Percentage** |
|:----------------:	|:------------:	|
| Bruno Barros     	|      25%     	|
| Diogo Campos     	|      25%     	|
| Fabio Caramelo   	|      25%     	|
| William Fukunaga 	|      25%     	|
