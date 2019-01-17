# Oneline-Cron-Backup
This is just a good way to do a one-line backup in cron, which emails its results to an email address.  I have used this in FreeNAS, pfSense, and many linux distros.

# The command
rsync -avz -e "ssh -p{SSH PORT}" /mnt/{Local Drive}/{Local Folder} root@{externalserver}:/{path/to/destination/folder} | mail -s "LOG - Backup - {folder}" {log email}

# The Requirements
So that this can seamlessly work automatically, you need to set up a ssh key to allow the source server to access the remote server passwordlessly.  I suggest not using root, however sometimes (such as in FreeNAS) this is necessary due to folder permissions.

* ToDo: Create a script to make this easy for others to use.  ETA: This millennium.
