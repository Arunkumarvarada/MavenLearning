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

=====================================================================================
