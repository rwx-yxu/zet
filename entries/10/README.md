# GPG Key Github Authorisation

I had finally gotten around to get GPG setup for signed commits
by following the github article for this[^1]. Signed commits are important
when verifying the commit is from the original creator.

I did run into couple of issues. The first of which was adding the
public GPG key to github when trying to copy the key from windows
terminal[^2]. The format is wonky to say the least from incorrect spacing
for couple of lines to wrong ordering.

The core issue seemed to be the formatting of the GPG key itself. There
just needed to be an additional white space line between the first
comment and the public key.

Secondly, I also needed to run this additional git command for signed
commits `git config --global user.signingkey <Key>` for signed commits.
Otherwise, I received an error `Failed to sign the data` message.

Another useful command is `gpg --list-secret-keys --keyid-format=long`
to view the keys on machine.

[^1]:https://docs.github.com/en/authentication/managing-commit-signature-verification/generating-a-new-gpg-key
[^2]:https://docs.github.com/en/authentication/managing-commit-signature-verification/adding-a-gpg-key-to-your-github-account
