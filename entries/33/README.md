# Beware of replacing GPG keys
For the past month or so I have been using an expired GPG key to sign my commits for GitHub. This
wasn't really ideal as I manually extended the expire time on my local machine to allow for the
commits to go through but GitHub still recognises the commits are from an expired key.

Therefore, I decided today to generate a new GPG key and replace the old one with a new duration.
It's normal in security to set a duration for things rather than have a key with no expire duration.
Little did I know that by removing the old key from GitHub, all of my commits that were signed would
now be unverified...

I wasn't expecting this and it seems that it is probably best to keep it like that rather than
rebase all of my repositories with the new key which would generate new commit hashes. Not too bad
since all of my repositories are for myself but it is not ideal either.

It doesn't seem ideal to me to have the old expired key floating around as well so the solution
seems to just keep it as it is and carry on with this new key for commits. Despite how it will bug
me looking at the commit history and seeing the unverified commits when they were verified.
