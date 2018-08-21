# CasperJS and PhantomJS binaries

###### This is a full [CasperJS](https://github.com/casperjs/casperjs) library with an added [PhantomJS](http://www.phantomjs.org/) binary for Linux x64


CasperJS is a navigation scripting & testing utility for PhantomJS.
It eases the process of defining a full navigation
scenario and provides useful high-level functions, methods & syntactic sugar for doing common
tasks such as:

- defining & ordering [navigation steps](http://docs.casperjs.org/en/latest/quickstart.html)
- [filling forms](http://docs.casperjs.org/en/latest/modules/casper.html#fill)
- [clicking links](http://docs.casperjs.org/en/latest/modules/casper.html#click)
- [capturing screenshots](http://docs.casperjs.org/en/latest/modules/casper.html#captureselector) of a page (or an area)
- [making assertions on remote DOM](http://docs.casperjs.org/en/latest/modules/tester.html)
- [logging](http://docs.casperjs.org/en/latest/logging.html) & [events](http://docs.casperjs.org/en/latest/events-filters.html)
- [downloading](http://docs.casperjs.org/en/latest/modules/casper.html#download) resources, even binary ones
- catching errors and react accordingly
- writing [functional test suites](http://docs.casperjs.org/en/latest/testing.html), exporting results as JUnit XML (xUnit)

Browse the [sample examples repository](https://github.com/casperjs/casperjs/tree/master/samples).
Don't hesitate to pull request for any cool example of yours as well!

**Read the [full documentation](http://docs.casperjs.org/) on casperjs documentation website.**

## Show me some code!

First [install CasperJS](http://docs.casperjs.org/en/latest/installation.html), we'll use 1.1 beta here.

Sample test to see if some dropdown can be opened:

```javascript
casper.test.begin('a twitter bootstrap dropdown can be opened', 2, function(test) {
    casper.start('http://getbootstrap.com/2.3.2/javascript.html#dropdowns', function() {
        test.assertExists('#navbar-example');
        this.click('#dropdowns .nav-pills .dropdown:last-of-type a.dropdown-toggle');
        this.waitUntilVisible('#dropdowns .nav-pills .open', function() {
            test.pass('Dropdown is open');
        });
    }).run(function() {
        test.done();
    });
});
```

Run the script:

![](http://cl.ly/image/271e2i403A0F/Capture%20d%E2%80%99%C3%A9cran%202013-01-20%20%C3%A0%2009.26.15.png)
