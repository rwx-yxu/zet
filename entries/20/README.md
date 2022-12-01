# Do not use web.xml along with @WebServlet notation in tomcat 9

I just figured out that tomcat maps urls weirdly if there is the
presence of both a web.xml file and @WebServlet. I think that tomcat is
trying to apply both which results in urls not being able to be mapped
for new servlets.

Reason for this is that, the base template code provided by the labs had
a web.xml file and when I tried to use the notation, Eclipse also added
the config to the xml as well which resulted in tomcat not being able to
route the request to the servlet.

Choose one or the other method.
