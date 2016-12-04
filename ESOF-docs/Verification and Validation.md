![FEUP image](https://sigarra.up.pt/feup/pt/WEB_GESSI_DOCS.download_file?p_name=F-370784536/logo_cores_oficiais.jpg)

#Assignment 4: Verification and Validation

##Software Testability and Reviews

###Controllability
* Ability to easily control the inputs to produce a specific output

Leaflet's tests are generally flexible and easily malleable, although for specific modules modifying them is more difficult.

The following snippet, which tests the function ```L.Util.splitWords()```, is an example of an easily controllable test. In this paticular scenario, the function splits the string *'foo bar baz'* into the array *['foo', 'bar', 'baz']* and if we wanted to obtain the array *['esof', 'docs']* we would simply input the string *'esof docs'*.
```javascript
describe('#splitWords', function () {
	it('splits words into an array', function () {
		expect(L.Util.splitWords('foo bar baz')).to.eql(['foo', 'bar', 'baz']);
	});
});
 ```
 
On the other hand, there are some tests that are state-dependent and thus don't have high controllability. Since JavaScript has multiple implementations depending on the browser, some functionalities have to be tested for each of the specific browsers (we talk about this in detail in the Heterogeneity section). We consider that Leaflet handles this issue very well, by enabling the user to run the tests in the desired browsers.

###Observability
* Ability to easily observe the test results

By running tests in ```spec/index.html```, the page will indicate specifically which test failed and which ones passed, showing the expected and the obtained results, although it will not indicate test coverage.

To get a detailed overview of the test coverage, Jake will provide the overall details from each folder, including statements, branches, functions and lines, in the file ```coverage/<environment>/index.html```.

The tests results are easily observable, as it is easy to understand what is the expected output and the obtained one.

###Isolateability
* Ability to test specific components in isolation

Leaflet is organized into modules and the isolateability depends on the complexity of the module. For the simpler ones, the tests have high isolateability, while the higher level ones have multiple dependencies that makes it harder to isolate them.

The Leaflet tests adopt the following pattern: 
* create a few objects necessary for the tests;
* run tests and using those objects;

This means that there will be one or more tests that makes use of one or more object, reducing the degree to which each test is isolated.

###Separation of Concerns
Each test is responsible for a single functionality.

###Understandability
Using the ```spec/index.html```, there is a brief description to the test being done. Another testing method would not display a description of the tests.

###Heterogeneity
* Heterogeneity is when different technologies require different test cases.

As mentioned in the Controllability section, Leaflet can run on different browsers and each of them has a different JavaScript implementation, requiring browser-specific tests. In order to execute the tests in a specific browser, a flag should be added to the command, for example: ```jake test --chrome```. This way, the test will be executed on Chrome and the results are going to be displayed on the console. If no browser is selected, the test environment will run in the PhantomJS engine.

In Leaflet the tests are heterogeneous since the tests don't always follows the same type of test, changing the way the code is tested.

##Test Statistics and analytics
For Leaflet, running test cases is very simple. It is described in the [CONTRIBUTING.md](https://github.com/Leaflet/Leaflet/blob/master/CONTRIBUTING.md) file and the tester only needs to install PhantomJS and a Node.js package called Jake.

To run the tests, run the command:
```
jake test
```

In order to get the coverage, run:
```
jake test -cov
```

Another option is simply to open ```spec/index.html``` that makes use of mocha nodeJS manager and the tests will run automatically.

As mentioned before, Leaflet uses Jake. With this build tool, tests can be easily executed as well as test coverage.
There are around 540 tests executed on Leaflet's test suite. This tests cover several components. However, this is not enough to assure that Leaflet is working well. In order to check this, it is necessary to check test coverage.
The test coverage results are shown below:
![Test Coverage](https://raw.githubusercontent.com/DiogoMCampos/Leaflet/ESOF-Documentation/ESOF-docs/resources/TestCoverage.png)
As seen in the results, Leaflet tests have a good coverage with an average of 70%. However, some components could have a better coverage, for example the Handler which has a lower coverage.


##Bug identification and correction
In order to contribute to the repository we started by trying to find a bug that wasn't descripted in the issues but that wasn't easy so after a long time searching and trying we gave up and we opted by selecting a bug.
We took a look into issue number [5116](https://github.com/Leaflet/Leaflet/issues/5116) and tried to figure out what was wrong. With the recommendations given we tried to correct and reached a similar solution that another user had reached. However, he said his solution didn't work. We tried to figure out what was wrong and we think we came to a conclusion. There were errors on the test scene provided, making it impossible to work. So we fixed the test scene and it worked out. We told them about our solution but until the deadline we don't know if our solution is acceptable.
Since we were determined to fix a bug, we looked for another issue. We ran into issue number [5107](https://github.com/Leaflet/Leaflet/issues/5107) and tested. We tested on the platforms the user said (Chrome Beta and Android 7.0) and our output didn't match the user's output. We got the desired output (same as other browsers and platforms) so we commented the issue.


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
