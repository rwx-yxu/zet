# Try catch blocks can hide errors

I have noticed an issue whilst debugging an exception I was doing for my
university assignment. This is in regards to a SQL statement connection
being closed when trying to execute SQL.

The exception was `java.sql.SQLException: No operations allowed after 
statement closed.` This as wrapped in a try catch block. When trying to
debug, the error suggested to me the statement object was closed.
I eventually found out that the actual error was 
`java.sql.SQLException: No operations allowed after connection closed.`
In relation to the SQL connection being closed rather than the statement
being closed. This exception wasn't flagged first since they were both
SQLException objects I wasn't able to easily determine which line was
the culprit because both the open statement line and execute SQL were in
the same try catch block.

I had found the actual error through putting both statements in separate
blocks. I have come to realise that try catch blocks can reduce code
readability. This is particularly there is the possibility of the same
exception being thrown. When debugging, it is useful to know where
exactly and error occurred in relation to the code. Try catch blocks
actually hide away the error after the main block of code in the catch
section. This can be unhelpful at times when there may be multiple lines
the try section that can throw the same exception.

Go on the other hand, as repetitive as it is, encourages the programmer
to deal with the error once encountered. I find that this approach is
actually good because it means that the errors are handled in response
to where the error actually happens.

Another view point may very well be that the code design that I have
written is poor which has lead me to this issue in Java. I accept that
this is also a possibility.
