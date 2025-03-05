# Remove symlinks on bash

To remove a symlink on bash:
* Check that the symlinks exist `ls -lah` in current directory symlinks will start with a `l` in the permissions letters.
* Run `unlink <first location from the above command>` this will remove both directories. Adding sudo may be required if it's in a `/` directory where the user doesn't own the directories

Found this useful removing a rouge version of python on my machine by removing the said python version symlinks in `/usr/local/bin/` directory
