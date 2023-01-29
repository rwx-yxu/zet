# Use Z.Vars.Get() to grab bonzai vars

When creating a new bonzai cmd leaf for a new branch, I was unable to get the cached vars
through the standard `x.Caller.Get("")` line because the reference is to the parent branch.

The cached var that I wanted to grab was `.apikey` which was unable to be found because the parent
branch was the default branch. In order for the var file to be found on my leaf, I had to rename the
cached name to `.branch.apikey`.

Alternatively, I found that calling `Z.Vars.Get(.apikey)` works.
