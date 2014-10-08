# Plugin modification Scenarios

Plugins should be easy to modify.  There are two scenarios where this may occur:

1. As a part of a LAB lesson, the user needs to modify the source code.  Ideally, plugins allow this modification to occur without a restart, and using only a text editor, so that it is easy to complete lessons.  Ability to edit files on the the filesystem is a great bridge to later functionality to allow editing them directly in the IDE.

2. As a part of learning and/or starting your own lesson, it should be as easy as copy-paste to start with an existing lesson and make a new one.  

# Plugin Authoring Scenarios

We want it to be easy to extend WebGoat.  Webgoat is extended using lessons, which teach a particular security topic.  There are two main scenarios in which a a user might add a lesson:

1. In-house.  In this case, the lessons are used for internal training, and are not intended to be contributed to the community. In this case:
    * The lesson source is separate from the WebGoat source
    * The user would probably prefer to use a binary distribution of Webgoat, so that they can periodically upgrade it very easily. IE, java -jar WebGoatBinary-exec-war.jar
    * When the user upgrades webgoat, they want their lessons to appear, but not to be overwritten
    * The user does not want to bother with a git clone
    * the user really doesnt want to deal with a Java IDE

2. Contributors. In this case, the user authors lessons with the intent of contributing them back to the community. In this case:
    * The user is best served by starting with a git clone, because they eventually need to submit a pull request
    * The user runs WebGoat from source with mvn tomcat:run-war
    * It is highly desirable for the user to be able to re-load rules without restarting tomcat. Otherwise its just a huge pain to develop
    * A Java IDE is probably more likely here, but again it shouldnt require a restart to make changes.


