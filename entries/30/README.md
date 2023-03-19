# GPG Debugging
I just had an issue with GPG failing to sign my commits. The error message was as follows:

```
error: gpg failed to sign the data
fatal: failed to write commit object
```

Here are some useful steps to understand how to resolve.
* Rerun the commit with a git trace `GIT_TRACE=1 git commit`
* Run `gpg -bsau key_id` to see why status of the key
* In my case the key expired so there is a way to change the expired time without generating a new
  key all over again.
* `gpg --list-keys` will display all the gpg keys on the system.
* `gpg --edit-key gpg_id` the id is the second column next to the pub heading.
* This should open a gpg shell which you can now change the expired time with the command `expire`
  which should prompt you with options to change the time to.
* Note that once the expired time has changed, you may need to change the sub key as well. You will
  know this because of a prompt

```
  gpg: WARNING: Your encryption subkey expires soon.
  gpg: You may want to change its expiration date too.
```

* Change the expired sub key with the command in the gpg shell `key 1`

