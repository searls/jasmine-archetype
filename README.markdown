jasmine-archetype
=================
**A Maven Archetype for getting started with Jasmine JavaScript testing**

Usage
-----

Create a new Maven project that's set up to use jasmine-maven-plugin, replete with example specs.

    mvn archetype:generate \
    -DarchetypeRepository=http://searls-maven-repository.googlecode.com/svn/trunk/snapshots \
    -DarchetypeGroupId=searls \
    -DarchetypeArtifactId=jasmine-archetype \
    -DarchetypeVersion=0.11.1-SNAPSHOT \
    -DgroupId=com.acme \
    -DartifactId=my-jasmine-project \
    -Dversion=0.0.1-SNAPSHOT

This will create a project that looks something like this:

    |-- pom.xml
    `-- src
        |-- main
        |   `-- javascript
        |       `-- element_mover.js
        `-- test
            `-- javascript
                `-- element_mover_spec.js

To build the project and verify the Jasmine specs are executing, switch to the new project directory and build it:
    
    cd my-jasmine-project
    mvn clean package

If you want to experiment further, try adding a new spec to the existing `element_mover_spec.js` file, and open `target/ManualSpecRunner.html` 
in a browser, refreshing each time you change the source.  

Bonus Hint: every time you add a new JavaScript file to the project, the runner HTML will need to  be regenerated. This will happen on every
 full Maven build (m2eclipse should also do this while auto-building), but it can also be invoked from the command line with:
 
    mvn jasmine:generateManualRunner
