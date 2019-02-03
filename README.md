# socat-mailonconnection

sends mail with information about who and when connected to a specified port that should not be used anymore

proxy for legacy services that will go offline, but still have active ( or not updated ) systems accessing the resource,

it will proxy the port given as second argument to the same port on the first argument 

and the mail will be sent to root of whatever your mta thinks root is ,so setup your alias properly (or use e.g. mstmtp )

designed to run via supervisord(does not fork)


 example config snippet (adjust script path!):

[program:mysql-socat]

command=/bin/bash /etc/custom/socat-mailonconnection/spawn_socatmailer my-old-server-that-ends-soon.com 3306

stderr_logfile = /tmp/sqlsocat-stderr.log

stdout_logfile = /tmp/sqlsocat-stdout.log

