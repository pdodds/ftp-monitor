Simple FTP Monitor
==================

This is a very simple FTP monitor which supports the usual configuration capabilities to monitor one or more
remote FTP servers and then picking up files from one or more directories.  

You can specify the download type (binary/ascii) and also have file patterns.  Also you can tell it to keep a history of the files which have been downloaded so that only new files are picked up.

It is configured through a monitors.yml - which it will look for in the directory where the script is started.

The example shows all the available settings.

	monitored:
	   - id		      : example1
	     name             : Example FTP server
	     description      : This is an example of the FTP monitoring    
	     sleeptime        : 5 
	     ftp-server       : localhost
	     ftp-port         : 21
	     username	      : testuser
	     password         : testpassword
	     passive          : true
	     email_on_error   : true
	     email_from_alias : System
	     email_from       : test@localhost
	     email_to_alias   : System Support
	     email_to         : support@example.com
	     directories:
	        - id          : dir1
	          remote_path : /incoming
	          filename    : *.csv
	          local_path  : /tmp/dir1
	          ascii       : false
	          remove      : false
	          only_new    : true
	        - id          : dir2
	          remote_path : /outgoing
	          local_path  : /tmp/dir2
	          filename    : template*.dat
	          ascii       : true
	          remove      : false
	          only_new    : true