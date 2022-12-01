# Java dependencies vs Go

Today, I noticed the difference in library imports in Java compared to
go. I bring this up because my lab session required the use of external
Java libraries JAXB and gson for xml and json parsing. To import the
Java libraries, we had to place .jar files into lib folder of the
project directory. This can be done through the eclipse IDE.

The actual import line in Java can be too verbose which even the IDE
tries to hide from you.

This system is drastically different to go. Go defines the package
import origins directly in go.mod. Unused imports will be flagged by the
compiler and with the go language server, auto imports are possible
rather than manually selecting the import you want from the IDE.

I prefer the go way of managing dependencies because it reduces the
verbosity as well as enforcing cleaner code by flagging unused code.

Sending around .jar files for library imports does not seem like a good
idea for me. I know that maven and gradle exist specifically for this
reason but trying to just use Java should require this.
