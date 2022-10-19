---
title: cPanel & WHM Systems Administrator Exam (CWSA) Answers 2022
slug: cpanel-whm-system-administrator-exam-CWSA-answers
author: [stefanpejcic]
date: 2022-22-11
excerpt: "Answers to CWSA Exam"
tags: ["exams"]
---

In a cPanel & WHM environment, which of the following tools can be best described as the executable that reads the grants_cpuser.yaml file, then adds the corresponding grants to MySQL.

-   restoregrants

* * * * *

Which of the following MySQL/MariaDB-related variables can be controlled via an option found within WHM's Tweak Setting interface?

-   open_files_limit

* * * * *

Which of the following describes one of the important steps that should be taken after restoring a single database from a full cPanel backup, into a new database instance?

-   Associate the database and the database user with the cPanel user using the Database Map Tool.

* * * * *

If the MySQL processes are stopped using the kill -9 command, what can you expect to happen?

-   The severed writes on the databases will increase risk of database corruption.

* * * * *

Which of the following statements about InnoDB tablespaces are true?

-   They can be stored individually within a database folder, or lumped together into the ibdata1 file.

* * * * *

In a cPanel & WHM environment, which of the following files might you find in the /var/cpanel/databases directory?

-   dbindex.db.json

* * * * *

In a cPanel & WHM environment, which of the following tools' purpose can be described as the executable that is responsible for the initial setup of database mapping, as well as any updates that occur between versions?

-   setupdbmap

* * * * *

Which of the following pieces of information can you find in both the slow query log and the general query log?

-   The user who executed the query.

* * * * *

In a cPanel & WHM environment, which of the following tools is best described as the command-line equivalent of WHM's Database Map Tool interface?

-   dbmaptool

* * * * *

Most of the executables found within the /usr/local/cpanel/bin directory are not intended for standard usage by users, and are not developed to be user-friendly (frequently lacking any kind of help output or formal documentation). These are intended primarily for back-end and automated handling, as opposed to those executables found within the /usr/local/scripts (/scripts) folder.

There is at least one notable exception to this. Which of the following tools found within this path is actually recommended for server administrator use as needed, in certain circumstances?

-   dbmaptool

* * * * *

How should you enable the slow query log on a cPanel & WHM server?

-   Add "slow_query_log=1" to the mysqld section of the /etc/my.cnf configuration file.

* * * * *

Which of the following statements is not a legitimate SQL statement?

-   COPY

* * * * *

Which of the following variables in a cPanel & WHM server's /etc/my.cnf file are set by default?

-   default-storage-engine=MyISAM

* * * * *

In the context of a MySQL database, which of the following can best be described as an attribute used to sort or specify data, sometimes across tables?

-   Index

* * * * *

Which of the following best describes the role of the exim -bt command?

-   Prints the path that the message will take when Exim attempts delivery to a specified address.

* * * * *

Which of the following commands will remove all messages sent by the spammer@example.tld user within the last 30 minutes?

-   exiqgrep -f spammer@example.tld -y 1800 -i | xargs exim -Mrm

* * * * *

Which of the following describes the primary role of the exim -Mvb command?

-   Prints the message body when given the Exim ID.

* * * * *

Which of the following can be discerned from the Exim log entry shown below?

1YO6VR-00081w-7C => test test@cpanel.net R=virtual_user T=virtual_userdelivery

-   The message was delivered.

* * * * *

Which of the following Actions in a cPanel email filter will result in an incoming message being rejected without sending any notifications?

-   Discard Message

* * * * *

A particular type of email filter is stored in the /etc/vfilters/ directory. Which of the following types of filters are these?

-   Account-level email filters.

* * * * *

Of the following mailbox formats, which of these are supported for use in cPanel & WHM environments?

-   MailDir

* * * * *

The highlighted part of the message below indicates which of the following values?

2015-02-18 09:25:42 1Y06VR-0000Iw-7C= test@cptest.test H=localhost ([10.5.2.154]) [::1]:38793 P=esmtpa A=dovecot_login:test@cptest.test S=724 id=afc7s4294172a42cd5ce527636d7b74c.squrrel@10.6.2.152 T="test discard filter" for filters@cptest.test

-   The Exim ID

* * * * *

What is the role of the -y flag when used with the exiqgrep utility?

-   Messages older than the number of seconds given.

* * * * *

In an Exim log entry, the cwd value indicates which of the following?

-   The user executing the command.

* * * * *

Which of the following can be discerned from the Exim log entry shown below?

1YOv2S-0005IY-7r == test@cptest.test R=virtual_user T=virtual_userdelivery

-   The message was deferred.

* * * * *

Which of the following best describes the role of the exim -Mrm command?

-   Deletes the message based on a given the Exim ID.

* * * * *

Given the following options, which one would be descriptive of behavior most likely to indicate that a spam problem is occurring?

-   A large number of failed messages reported.

* * * * *

Which of the following best describes the role of the exim -bpc command?

-   Prints the number of messages in the mail queue.

* * * * *

Which of the following terms can best be described as an input stream where data is sent to and read by a program?

-   STDIN

* * * * *

Which of the following components can be described as a specific SAPI that provides functionality in a module that behaves as if it had been compiled into Apache itself, handling appropriate requests without producing new, non-Apache processes?

-   DSO

* * * * *

Referencing the Apache error log entry shown below, which of the following options best describes the yellow-highlighted portion of the log entry?

[Fri Sep 09 10:42:29.902022 2011] [core:error] [pid 35708:tid 4328636416] [client 72.15.99.187] File does not exist: /usr/local/apache2/htdocs/favicon.ico

-   The inbound IP address of the node that requested the item that caused the error message.

* * * * *

How does the scl command know which version of PHP it should use?

-   You provide the PHP version as a command-line argument.

* * * * *

In a server running cPanel & WHM, how can you create a new EasyApache 4 profile from within the server's command-line?

-   In the file system, make a copy of an existing profile's file, edit it with any desired changes, then save the new file.

* * * * *

Which of the following options could be described as a repository for PHP extensions?

-   pecl

* * * * *

When administering a server running cPanel & WHM, which of the following commands contains the appropriate paths and arguments needed to install an EasyApache 4 profile from the command-line?

-   /usr/local/bin/ea_install_profile --install /etc/cpanel/ea4/profiles/cpanel/default.json

* * * * *

Which of the following terms can best be described as the destination where a process can write normal output to, usually being to the terminal, server console ("screen"), unless redirected?

-   STDOUT

* * * * *

Which of the following yum commands would remove, or uninstall, the mod_speling RPM?

-   yum remove ea-apache24-mod_speling

* * * * *

If a file or directory in a path being served by Apache contains incorrect permissions or uses improper user/group ownership values, which of the following HTTP status codes might you see in the Apache logs if a client were to request one of the affected paths?

-   403

* * * * *

Which of the following options describes the best way for you to enable the experimental repository for EasyApache 4, when operating within a cPanel & WHM environment?

-   Perform the following command from the command-line, as root or equivalent: yum install ea4-experimental

* * * * *

Which of the following options indicates the HTTP status code that produces the error shown below?

Unauthorized. A password is needed to see this page. The browser should prompt for a username and password.

* * * * *

-   401

In a server running cPanel & WHM, which of the following options describes a method for changing the system's default PHP version via the command-line?

-   Use the /usr/local/cpanel/bin/rebuild_phpconf command.

* * * * *

Which of the following options indicates the HTTP status code that produces an error like the one shown below?

Forbidden. Access was denied to at least one relevant file.

-   403

* * * * *

Which of the following file names follows the naming convention for a BIND/named zone file?

-   domain.net.db

* * * * *

On a cPanel & WHM environment, the system stores DNS zone template files within which of the following paths?

-   /var/cpanel/zonetemplates

* * * * *

After you make a number of zone file changes in different zones, if you want to ensure that caching nameservers know to load the new information from your server, which of the following, single procedures can you perform to accomplish this?

-   Batch Zone Update

* * * * *

Which of the following is the first nameserver that the resolver queries to determine the address of the TLD nameserver?

-   The root nameserver.

* * * * *

If you create a customized DNS zone template from the command-line, which of the following would be a correctly-named custom template file name?

-   root_templatename

* * * * *

In a BIND/named configuration, you can modify the level of detail that is provided to remote servers regarding which of the following types of information?

-   Host application details indicating version and server data regarding your BIND/named installation.

* * * * *

On a cPanel & WHM environment, the system stores the private/public keys for DKIM in which of the following paths?

-   /var/cpanel/domain_keys

* * * * *

Which of the following utilities included with BIND/named can be used to troubleshoot malformed zone files?

-   named-checkzone

* * * * *

Which of the following utilities can be used to administer a BIND/named server remotely?

-   rndc

* * * * *

Which of the following DNS-related command-line utilities would provide you with similar results to those given by the dig utility, and is used for essentially the same purposes?

-   nslookup

* * * * *

In a BIND/named configuration file, which of these logging categories encompasses all categories that have not already been explicitly configured to use another channel?

-   default

* * * * *

What does the acronym TLD represent, as in for a "TLD nameserver"?

-   Top-level Domain

* * * * *

When operating within a cPanel & WHM server, which of the following indicates the best method to restart the DNS server from the command line?

-   /scripts/restartsrv_named

* * * * *

To retrieve the IPv6 record of a domain, you would query for which of the following records in a domain?

-   AAAA

* * * * *

Which of the following terms is used, particularly in spam-training applications, to describe the opposite of spam, meaning legitimate, solicited messages that are not considered spam?

-   Ham

* * * * *

Which of the following applications can be described as a tool used to batch update Bayesian databases?

-   sa-learn

* * * * *

Assume the host environment is a default cPanel & WHM installation. Based on the log entry shown below, identify from the options available which log file that this entry would be found in:

Warning: "SpamAssassin as cars detected message as spam (108.6)"

-   /var/log/maillog

* * * * *

Which options must you pass to the sa-learn program if you want it to update the Bayesian database with information from a mailbox?

-   --spam/--ham
