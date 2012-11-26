# Seafile data backup #

Seafile data are all stored in the installation directory, so just back up whole directory.

We use rsync on our backup machine to pull Seafile installation directory on machine A. Command looks like:

   mkdir /backup

   rsync -azv --delete user@A:/path/to/your/seafile /backup/

Also you might want to set up a script framework that calls such a command via cron. Rule looks like:

     0 3 * * * rsync -azv --delete user@A:/path/to/your/seafile /backup/

This will perform backup operation on 3:00 am everyday.     
