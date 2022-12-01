# Do not use dashes for go package names

Go linter will not like the fact that there is a dash for a package name
import. I had encountered this when trying to import a module with a
dash in the name go-term. In the end, I changed the repo and module name
and package to term.
