# Installing WebGoat

This guide describes how to install and run WebGoat. 

# WebGoat Versions

WebGoat contains 28 lessons, 4 labs, and 4 developer labs. Two distributions are available, depending on what you would like to do.

  1. *Easy-run package.* The easiest version to play with. The easy-run package is a platform-independent executable jar file, so it has minimal muss and fuss. Since this distribution does not include source, you cannot complete the 4 developer labs.  *Pre-requisites* : Java JRE >= 1.6	

  2. *Source distribution.*  Allows modifying the source code of WebGoat.  WebGoat is a standard Maven project. This is the right choice if you wish to complete the developer labs, or you wish to contribute to WebGoat.  *Pre-requisites* -- Java JDK >= 1.6, Maven  >= 3
	
Use this feature comparison to choose the right distribution for you
	
Feature			| Easy-run| Source 
------------------------|------------|---------
Lessons			| X	| X 
Standard Labs		| X	| X 
Admin Report Card	| X	| X 
Developer Labs		|	| X	


# Downloading
	Easy-run distribution: https://webgoat.atlassian.net/builds/browse/WEB-DAIL/latestSuccessful/artifact/JOB1/WebGoat-Embedded-Tomcat/WebGoat-6.0-SNAPSHOT-war-exec.jar  
	Source distribution: https://github.com/WebGoat/WebGoat
	
# Quick Start -- Easy Run
	1. *Install a Java JVM*.  You can get one here http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html
	2. *Download WebGoat*. https://webgoat.atlassian.net/builds/browse/WEB-DAIL/latestSuccessful/artifact/JOB1/WebGoat-Embedded-Tomcat/WebGoat-6.0-SNAPSHOT-war-exec.jar 
	3. *Make Sure Java is in your path* This should already be the case after you install Java. If it is not, add it to your path
	4. *Run WebGoat* by executing this command in the same directory you downloaded WebGoat into:
	```
		java -jar WebGoat-6.0-SNAPSHOT-war-exec.jar
	```
	5. *Verify it worked* by pointing your browser to http://localhost:8080/WebGoat. You should see a signin screen.  
	
	That's it!  If you need to change the port or other options, you can use --help to display more options. For example, to run WebGoat on port 9090, you can run:
	```
		java -jar WebGoat-6.0-SNAPSHOT-war-exec.jar -port 9090
	```

# Quick Start -- Source Distribution
	
	1. *Install the Prerequisites.* Minimally, this is a JDK and Maven, but it may include an IDE Git if you do not have them.
	2. *Download the source* from https://github.com/WebGoat/WebGoat You'll want to clone it if you intend to contribute, otherwise you can just download an archive
	3. *Run WebGoat with Maven* Change to the project location, and run:
	
	```
		mvn tomcat:run
	```
	4. *Verify it worked* by pointing your browser to http://localhost:8080/WebGoat. You should see a signin screen. 
	5. *Open with your IDE* to modify the source.  WebGoat is a standard maven project, so you should be able to import it with most any IDE
	
	

# Prerequisites
	
	All you need to run WebGoat is a Java VM, but you'll need the standard Java development tooling to use the source distribution. 

## Easy-run 

	Any JRE >= 1.6 will work.  You an download one for your platform here:
	
		http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html
	
## Source Distribution Prerequisites
	
	To run from source, you'll need a standard Java development environment. If you are already a Java developer, you've likely got the tooling you need.  
	
	1. *Java JDK*.  A JRE distribution will not do. We recommend version 7:
	
		http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html
		
	2. *Maven* We recommend maven 3.2.3.  Maven is all that is required to compile, package, and run WebGoat.
	
		http://maven.apache.org/
		
		Note:  Many IDE's come bundled with Maven already, so you may not need to download separately
	
## Optional Items, especially if you are contributing to WebGoat
	
	Depending on your preferences, you may want a few other items: 
	
	1. *Java IDE (Optional)*  A Java IDE is highly recommended if you will be contributing to WebGoat, or otherwise spending a lot of time in the WebGoat source code.  Any Java IDE with Maven support will do.  If you are open, we recommend NetBeans 8, JavaEE edition, because it includes all of the other software you will need
		
		https://netbeans.org/downloads/
		
	We recommend the Netbeans JavaEE distribution, which includes maven 3, git support, and Tomcat as well.
	
	2. *Git (Optional)* Only if you wish to contribute to WebGoat. You have serveral choices for Git support:
		* `Netbeans`: Git support is built in
		* `Eclipse` : we recommend  the egit plugin
		* Native installation of git ( depending on your operating system)
		
	3. *Your Own Servlet Container (Optional)*  If you insist, you can install WebGoat in your own servlet container.  This is *NOT* the recommended method, as it requires you to add webgoat users to your container configuration.
	
	
	
	