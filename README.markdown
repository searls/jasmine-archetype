jasmine-archetype
=================
**A Maven Archetype for getting started with Jasmine JavaScript testing**

This archetype is designed to get you up-and-running quickly with the [jasmine-maven-plugin](http://github.com/searls/jasmine-maven-plugin).

Usage
-----

Create a new Maven project that's set up to use jasmine-maven-plugin, replete with example specs.

    mvn archetype:generate \
    -DarchetypeGroupId=com.github.searls \
    -DarchetypeArtifactId=jasmine-archetype \
    -DarchetypeVersion=RELEASE \
    -DgroupId=com.acme \
    -DartifactId=my-jasmine-project \
    -Dversion=0.0.1-SNAPSHOT

If you're on Windows or if your shell doesn't like the newlines above, here's the same command in a single line:

    mvn archetype:generate -DarchetypeGroupId=com.github.searls -DarchetypeArtifactId=jasmine-archetype -DarchetypeVersion=RELEASE -DgroupId=com.acme -DartifactId=my-jasmine-project -Dversion=0.0.1-SNAPSHOT

This will create a project that looks something like this:

    |-- pom.xml
    `-- src
        |-- main
        |   `-- javascript
        |       `-- element_mover.js
        `-- test
            `-- javascript
                `-- element_mover_spec.js

To build the project and verify the Jasmine specs are executing, switch to the new project directory and start the server:

    cd my-jasmine-project && mvn jasmine:bdd

Then you should be able to go to http://localhost:8234 in a browser and watch your specs execute. 

Adding the archetype catalog to m2Eclipse
-----------------------------------------

To create a new project from this archetype from within Eclipse, its archetype catalog will need to be added. The process goes something like this (and hardly seems worth the effort over doing it from command line):

1. File -> New Project... -> Maven Project
2. Click 'Next'
3. Select the jasmine-archetype and continue by clicking 'Next'
4. Make yourself a sandwich or otherwise reward yourself
