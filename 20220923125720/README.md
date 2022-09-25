# Output JSON in Golang template
You can use Template.JS after JSON marshall to render JSON into a golang template. This is
useful if you want to inject JSON data into a JavaScript framework
without needing to call a fetch from a separate endpoint.

This should not be used from untrusted JSON sources! Use JSON unmarshal
first and then pass it through to template.

Related:
  * (Template.JS docs)[https://pkg.go.dev/html/template#JS]

Tags:
    #Golang #JSON
