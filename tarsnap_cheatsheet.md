 - **Backup** : `tarsnap -c -f <backup name> <dir>`. As Root-user
 - **Recover**: `tarsnap -x -f <backup name>` restores (and overwrites) everything to recreate snapshot at backup time. Optionally add `<dir>` or `<file>` to just restore a file or a dir (without leading `/`).
 - **Show** `tarsnap --list-archives | sort`
 - **Delete** 'tarsnap -d -f <backup name>` deletes older backup

The config file can be found in ~/etc/tarsnap.conf


See more at https://www.tarsnap.com/usage.html

