# Disable JavaScript validation in Eclipse.

Google app engine will not deploy from eclipse if there are any errors
what so ever even if the "errors" are in JavaScript files.

Even if the JS is completely fine when testing in browser, Eclipses own
validator will prevent you from deploying to app engine.

The solution is to disable the validator which is buried in the
preferences menu.

