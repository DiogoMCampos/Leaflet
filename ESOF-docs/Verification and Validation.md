![FEUP image](https://sigarra.up.pt/feup/pt/WEB_GESSI_DOCS.download_file?p_name=F-370784536/logo_cores_oficiais.jpg)

#Assignment 4: Verification and Validation

##Software Testability and Reviews

###Controllability
For Leaflet, running test cases are very simple. It is described in the [CONTRIBUTING.md](https://github.com/Leaflet/Leaflet/blob/master/CONTRIBUTING.md) file and it says that the tester only needs to install nodeJS package called Jake and then run the command 'jake test --cov'.

##Test Statistics and analytics
As mentioned before, Leaflet uses Jake. With this build tool, tests can be easily executed as well as test coverage.
There are around 540 tests executed on Leaflet's test suite. This tests cover several components. However, this is not enough to assure that Leaflet is working well. In order to check this, it is necessary to check test coverage.
The test coverage results are shown below:
![Test Coverage](https://raw.githubusercontent.com/DiogoMCampos/Leaflet/ESOF-Documentation/ESOF-docs/resources/TestCoverage.png)
As seen in the results, Leaflet tests have a good coverage with an average of 70%. However, some components could have a better coverage, for example the Handler which has a lower coverage.


##Bug identification and correction

##Group members
*   [Bruno Barros](https://github.com/BrunoBarros21) - up201405249@fe.up.pt
*   [Diogo Campos](https://github.com/DiogoMCampos) - d.diogocampos@gmail.com
*   [Fábio Caramelo](https://github.com/Caramelo18) - up201404783@fe.up.pt
*   [William Fukunaga](https://github.com/williamnf) - up201405119@fe.up.pt

##Contributions

|       **Names**   | **Percentage**|
|:----------------:	|:------------:	|
| Bruno Barros     	|           	|
| Diogo Campos     	|           	|
| Fabio Caramelo   	|           	|
| William Fukunaga 	|           	|
