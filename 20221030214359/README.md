#Thermal printers are unique
I have been working with thermal printing lately and they are very
unique with respect to language output.

Thermal printers follow the esc pos standard defined by epson when it
comes to controlling output with special character sequences.

Each printer though can only print out specific languages that have been
set for the machine you are working on. Each printer has a `code page`
set which contain common ascii characters for different languages.
Reason for the code page set is because printers do not print unicode
directly. They instead use code pages to interface with difference
character sets. This means that some printers will not have a language
you may need.

This can be tricky when trying to find the right one to purchase if you
want to print out something other than English.

Tags:

    #printing #languages
