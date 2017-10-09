# MavenLearning


Getting started with Maven
==========================================
Project Creation:
==================
Create Java project
=====================
mvn archetype:generate
-DgroupId=org.yourcompany.project
-DartifactId=application

Create web project
==========================
mvn archetype:generate
-DgroupId=org.yourcompany.project
-DartifactId=application
-DarchetypeArtifactId=maven-archetype-webapp

Create archetype from existing project
mvn archetype:create-from-project

Useful command line options
-DskipTests=true compiles the tests, but skips

running them
-Dmaven.test.skip=true skips compiling the tests


Maven phases
============================================================================================
clean — delete target directory

validate — validate, if the project is correct

compile — compile source code, classes stored in target/classes

test — run tests

package — take the compiled code and package it in its distributable format, e.g. JAR, WAR

verify — run any checks to verify the package is valid and meets quality criteria

install — install the package into the local repository

deploy — copies the final package to the remote repository and does not run them

================================================================================
Useful command line options
===========================================================================================
-DskipTests=true compiles the tests, but skips

running them
-Dmaven.test.skip=true skips compiling the tests and does not run them

-T - number of threads:
 -T 4 is a decent default
 -T 2C - 2 threads per CPU
 
-rf, --resume-from resume build from the specified project

-pl, --projects makes Maven build only specified modules and not the whole project

-am, --also-make makes Maven figure out what modules out target depends on and build them too

-o, --offline work offline

-X, --debug enable debug output

-P, --activate-profiles comma-delimited list of profiles to activate

-U, --update-snapshots forces a check for updated dependencies on remote repositories

-ff, --fail-fast stop at first failure

