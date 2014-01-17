UnixSafeRm
====
Four bash scripts to use in place of the default rm command. 
• *newrm* - Instead of completely removing files, moves them to a hidden directory in the users home folder, not meant to be called explicitly

• *logrm* - logs the removing of a file to both a system log, and optionally (enabled by default) a .remove.log file in the users home directory. *logrm* calls *newrm* 

• *unrm* a utility for undeleting files. Without any arguments, it lists all of your removed files by date, with an argument file name supplied, it restores the file in the current working directory

• *clearRemovedFiles* - A script meant to be run as a cronjob that clears out the deleted files directory and the remove log back 3 months, 'empties the trash'. Without installing this, you'll have to empty the deleted directory and log manually or you can run out of space. 

Example crontab (assuming all of these files are in your crontab's path)

 	0 3 1 * * clearRemovedFiles
 	#this runs at 3:00AM on the first day of every month