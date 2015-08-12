# Windows Event Logs

## Import Windows Event Logs from a Log Collector into Logstash

The files in this folder are intended to allow you to import Windows Event Logs from a Windows Event Log Collector.  This file will not teach you how to set up a Windows Log Collector, however you can access the NSA's document on how to do so [here](https://www.nsa.gov/ia/_files/app/spotting_the_adversary_with_windows_event_log_monitoring.pdf)

Because you will be receiving the event logs in JSON format, the filters are very simple.  Simply link the files in this directory from your conf.d directory.  You may wish to change the port on the input filter.  Make sure that your filewall is configured to allow the traffic through as well.  Restart logstash and you should be ready to receive logs.

In order to set this up you will need to use the program *nxlog*.  I've included the *.msi* in the additional_files folder.  I've also included a *nxlog.conf* file to use.  Simply install nxlog on the Windows Event Log Collector.  Then go to the conf folder within the installation and insert *nxlog.conf* I've included.  You will need to change the IP Address and the port number at the bottom of the file.  Then restart the nxlog service.  To ensure that nxlog is working properly you should check in the <replace with proper directory> folder and read the .txt file.  It should be obvious if nxlog has encountered a bunch of errors.  The *nxlog.conf* file is very finicky about white space and some other things.  It can take some elbow grease to get working.  If your nxlog is up and running then you should now be sending logs to Logstash.




