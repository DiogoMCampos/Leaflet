![FEUP image](https://sigarra.up.pt/feup/pt/WEB_GESSI_DOCS.download_file?p_name=F-370784536/logo_cores_oficiais.jpg)

#Assignment 4: Verification and Validation

##Software Testability and Reviews

###Controllability
For Leaflet, running test cases IS very simple. It is described in the [CONTRIBUTING.md](https://github.com/Leaflet/Leaflet/blob/master/CONTRIBUTING.md) file and the tester only needs to install PhantomJS and a Node.js package called Jake. 

To run the tests, run the command:
```
jake test
```

In order to get the coverage, run:
```
jake test -cov
```

Another option is simply to open ```spec/index.html``` that makes use of mocha nodeJS manager and the tests will run automatically.

###Observability
To get a detailed overview of the test coverage, Jake will provide the overall details from each folder including statements, branches, functions and lines.
In the case of ```spec/index.html```, the tests will indicate specifically which test fails and passes though, it will not indicate test coverage.

###Isolate ability
The Leaflet tests adopt the following pattern: create a few objects necessary for the tests. After that it will analyze according to those objects. This means that there will be one or more tests that makes use of one or more object.

###Separation of Concerns
Each test is responsible for a single functionality.

###Understandability
Using the ```spec/index.html```, there is a brief description to the test being done. Another testing method would not display a description of the tests.

###Heterogeneity


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
