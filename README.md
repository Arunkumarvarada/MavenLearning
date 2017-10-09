# MavenLearning



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

Useful Plugins:
===========================================================================================

Help plugin — used to get relative information about a project or the system.

mvn help:describe describes the attributes of a plugin

mvn help:effective-pom displays the effective POM as an XML for the current build, with the active profiles factored in.

Dependency plugin — provides the capability to manipulate artifacts.

mvn dependency:analyze analyzes the dependencies of this project

mvn dependency:tree prints a tree of dependencies

Compiler plugin — compiles your java code.

Set language level with the following configuration:

<plugin>
 <groupId>org.apache.maven.plugins</groupId>
 <artifactId>maven-compiler-plugin</
 artifactId>
 <version>3.6.1</version>
 <configuration>
 <source>1.8</source>
 <target>1.8</target>
 </configuration>
</plugin>

Version plugin — used when you want to manage the versions of artifacts in a project's POM.

Wrapper plugin — an easy way to ensure a user of your Maven build has everything that is necessary.

Spring Boot plugin — compiles your Spring Boot app, build an executable fat jar.

Exec — amazing general purpose plugin, can run arbitrary commands :) 

Maven Dependency Plugins Overview:
=========================================

The Dependency plugin has several goals:

dependency:analyze analyzes the dependencies of this project and determines which are: used and declared; used and undeclared; unused and declared.

dependency:analyze-dep-mgt analyzes your projects dependencies and lists mismatches between resolved dependencies and those listed in your dependencyManagement section.


dependency:analyze-only is the same as analyze, but is meant to be bound in a pom. It does not fork the build and execute test-compile.

dependency:analyze-report analyzes the dependencies of this project and produces a report that summarises which are: used and declared; used and undeclared; unused and declared.

dependency:analyze-duplicate analyzes the <dependencies/> and <dependencyManagement/> tags in the pom.xml and determines the duplicate declared dependencies.

dependency:build-classpath tells Maven to output the path of the dependencies from the local repository in a classpath format to be used in java -cp. The classpath file may also be attached and installed/deployed along with the main artifact.

dependency:copy takes a list of artifacts defined in the plugin configuration section and copies them to a specified location, renaming them or stripping the version if desired. This goal can resolve the artifacts from remote repositories if they don't exist in either the local repository or the reactor.

dependency:copy-dependencies takes the list of project direct dependencies and optionally transitive dependencies and copies them to a specified location, stripping the version if desired. This goal can also be run from the command line.

dependency:display-ancestors displays all ancestor POMs of the project. This may be useful in a continuous integration system where you want to know all parent poms of the project. This goal can also be run from the command line.

dependency:get resolves a single artifact, eventually transitively, from a specified remote repository.

dependency:go-offline tells Maven to resolve everything this project is dependent on (dependencies, plugins, reports) in preparation for going offline.

dependency:list alias for resolve that lists the dependencies for this project.

dependency:list-repositories displays all project dependencies and then lists the repositories used.

dependency:properties set a property for each project dependency containing the to the artifact on the file system.

dependency:purge-local-repository tells Maven to clear dependency artifact files out of the local repository, and optionally re-resolve them.

dependency:resolve tells Maven to resolve all dependencies and displays the version. JAVA 9 NOTE: will display the module name when running with Java 9.

dependency:resolve-plugins tells Maven to resolve plugins and their dependencies.

dependency:sources tells Maven to resolve all dependencies and their source attachments, and displays the version.

dependency:tree displays the dependency tree for this project.

dependency:unpack like copy but unpacks.

dependency:unpack-dependencies like copy-dependencies but unpacks.
