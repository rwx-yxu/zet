# Tomcat development without IDE
Background:
I wasn't able to use Eclipse during my university lab because the
workspace default directory that Eclipse requires to use wasn't being
mounted on start up...

Due to this, I explored the possibility to develop on a tomcat server
without the need of an IDE. This isn't covered at all in lectures or
labs but the IDE must be doing something.

Steps:
1. The starting point is the tomcat server that can be obtained from the
   tomcat site.
1. After unzipping, the structure is similar to existed projects. There
   is a start.sh file that can be executed to start the server in the
   bin folder.
1. Configs for the port can also be changed in the web.xml file.
1. Great, we now have a tomcat server that can start.
1. The tricky part is now to manually add in a servlet. Tomcat will not
   register .java files. Instead, tomcat will only register .class
   files.
1. The new servlet must be added to the `webcontent` folder.
1. The root servlet folder name will be registered in tomcat.
1. To convert a .java file to .class, you need to run `javac
   path-to.java` to compile to class file.
1. Work flow overall: edit .java file -> compile to .class file -> place
   .class file to webcontents folder -> reload tomcat server -> static
   files like html do not require reloading.

Overall, in someways working with tomcat without an IDE is easier
because, the java version used is the java that is in the path so there
isn't a requirement to mess around in Eclipse java version of a project.
.class files will run on any JVM. The new files and projects that an IDE
does are creating files from templates anyways. The UI makes it seem
more complicated than it is.

It would be nice to streamline the process this by having a powershell
script to watch a dev directory with the java code to compile to .class
and reload the tomcat server like an entr command in linux.

The biggest bonus that an IDE offers is auto formatting and auto package
imports. Notepad++ and vanilla VSCode does not offer this.

Overall, I had learnt a fair amount about tomcat internals and also what
is actually happening under the hood of some IDEs.

Tags:

    #java #ide #eclipse #tomcat

