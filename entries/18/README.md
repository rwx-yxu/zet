# Testing informs design decisions

I realised an example whereby taking into account testing has enforced a
better coding structure.

I have been working on a terminal package to implement ansi characters
and I haven't felt like I could have tested color output. So far, I have
been manually testing the outputs in a command.

When thinking if there is a way to test this, I realised that what I am
doing is actually providing a sample output / use case. This means that
I can use a sample package that will call the term package functions.

Instead of having two commands to output text colors. I will now have
one single command called sample to call from using arguments.

This means that I can test the individual functions that create the
string for the sample output.
