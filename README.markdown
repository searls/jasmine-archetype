jasmine-archetype
=================
**A Maven Archetype for getting started with Jasmine JavaScript testing**

This archetype is designed to get you up-and-running quickly with the [jasmine-maven-plugin](http://github.com/searls/jasmine-maven-plugin).

Usage
-----

Create a new Maven project that's set up to use jasmine-maven-plugin, replete with example specs.

    mvn archetype:generate \
    -DarchetypeRepository=http://searls-maven-repository.googlecode.com/svn/trunk/snapshots \
    -DarchetypeGroupId=com.github.searls \
    -DarchetypeArtifactId=jasmine-archetype \
    -DarchetypeVersion=1.0.2-SNAPSHOT \
    -DgroupId=com.acme \
    -DartifactId=my-jasmine-project \
    -Dversion=0.0.1-SNAPSHOT

If you're on Windows or if your shell doesn't like the newlines above, here's the same command in a single line:

    mvn archetype:generate -DarchetypeRepository=http://searls-maven-repository.googlecode.com/svn/trunk/snapshots -DarchetypeGroupId=com.github.searls -DarchetypeArtifactId=jasmine-archetype -DarchetypeVersion=1.0.2-SNAPSHOT -DgroupId=com.acme -DartifactId=my-jasmine-project -Dversion=0.0.1-SNAPSHOT

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
    
    cd my-jasmine-project && mvn clean package

Hint: If you want to experiment further, try adding a new spec to the existing `element_mover_spec.js` file, and open `target/ManualSpecRunner.html` 
in a browser, refreshing each time you change the source.  

Bonus Hint: every time you add a new JavaScript file to the project, the runner HTML will need to  be regenerated. This will happen on every
 full Maven build (m2eclipse should also do this while auto-building), but it can also be invoked from the command line with:
 
    mvn jasmine:generateManualRunner

Adding the archetype catalog to m2Eclipse
-----------------------------------------

To create a new project from this archetype from within Eclipse, its archetype catalog will need to be added. The process goes something like this (and hardly seems worth the effort over doing it from command line):

1. File -> New Project... -> Maven Project
2. Click 'Next'
3. To the right of the catalog drop-down, click 'Configure...' 
4. Click 'Add Remote Catalog...'
5. In the URL field, enter:

    URL: http://github.com/searls/jasmine-archetype/raw/master/archetype-catalog.xml

    Name: jasmine-archetype catalog

6. Back at the archetype selection screen, choose the newly created catalog
7. Check 'Include snapshot archetypes'
8. Select the jasmine-archetype and continue by clicking 'Next'
9. Make yourself a sandwich or otherwise reward yourself
