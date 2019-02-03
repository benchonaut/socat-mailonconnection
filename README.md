# socat-mailonconnection

sends mail with information about who and when connected to a specified port that should not be used anymore

currently fixed settings for mysql with sendmail , whois and host, 
proxy for legacy services that will go offline, but still have active ( or not updated ) systems accessing the resource,

designed to run via supervisord(does not fork), example config snippet (adjust script path!):

[program:mysql-socat]
command=/bin/bash /etc/custom/spawn_sqlsocatmailer
stderr_logfile = /tmp/sqlsocat-stderr.log
stdout_logfile = /tmp/sqlsocat-stdout.log

