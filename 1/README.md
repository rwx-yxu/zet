# Use absolute paths for cron tabs to execute binaries

Absolute paths should be listed for cron jobs when executing custom
binaries.

I recently put my routine executable in a cron job to execute at 6:30am
and it didn't execute come the morning because I hadn't used absolute
paths to the binary.

The error logs weren't particularly vague so I changed to absolute
paths and now it works.

