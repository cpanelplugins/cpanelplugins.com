---
title: cPanel Certified Partner Accreditation Exam (CPCP) Answers 2022
slug: cpanel-certified-partner-accreditation-exam-cpcp-answers
author: [stefanpejcic]
date: 2022-10-10
excerpt: "Answers to CPCP Exam"
---

cPanel Certified Partner Accreditation (CPCP) Exam is divided in 6 sections, first 5 consist of 40 questions each, and last section has only 10 questions.

- [Web Server Administration](#web-server-administration)
- [Domain Name Server (DNS) Administration](#domain-name-server-dns-administration)
- [Database Server Administration](#database-server-administration)
- [Mail Server Administration](#mail-server-administration)
- [Development for cPanel & WHM](#development-for-cpanel--whm)
- [Utilizing cPanel Support](#utilizing-cpanel-support)

## Web Server Administration

You deploy an updated website version, but it only displays a blank white page in Firefox and an HTTP Error in Chrome. You find an error in the site's PHP error log regarding a call to an undefined function named mysqli. What is the ideal next step in troubleshooting the situation?

- Confirm that the mysqli PHP extension is installed and if not, install it.

---

A customer's website uses PHP 8.0 with PHP-FPM as the PHP handler. They've created a php.ini file in their website's document root, but their changes are not being reflected. Despite performing the following troubleshooting steps, the issue persists:

Restarted the ea-php80 PHP-FPM service.
Restarted Apache.
Confirmed correct ownerships and permissions on the php.ini file.
Confirmed that the website's document root is, in fact, the directory they placed the php.ini file.

Of the following choices, which of these accurately describes the issue that is occurring here?

- An .htaccess file stored in public_html should be used instead, containing only the values that need to be altered from the global defaults.
 
---

You've deployed the new version of your site in a custom document root. You made sure to update all the appropriate cPanel files, rebuilt the Apache configuration file, and restarted both Apache and PHP-FPM. However, sometimes when you try to load the site the old version appears. Calling upon your Linux skills, you run some commands to glean some more information about what might be going on with the site or, more broadly, Apache:
 
```
# fgrep 'Upgraded: ea-apache24-1' /var/log/dnf.log.1
 2022-06-23T04:48:21+0000 DEBUG Upgraded: ea-apache24-1:2.4.54-1.el8.cloudlinux.x86_64
 # ps uU nobody
 USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
 nobody   1157144  0.0  0.2 215340  9112 ?        S    Jun27   0:00 /usr/sbin/httpd -k start
 nobody   1157145  0.0  0.2 215340  9112 ?        S    Jun27   0:00 /usr/sbin/httpd -k start
 nobody   1157146  0.0  0.2 215340  9112 ?        S    Jun27   0:00 /usr/sbin/httpd -k start
 nobody   1157147  0.0  0.2 215340  9112 ?        S    Jun27   0:00 /usr/sbin/httpd -k start
 nobody   1157148  0.0  0.2 215340  9112 ?        S    Jun27   0:00 /usr/sbin/httpd -k start
 nobody   1163083  0.0  0.2 215340  9188 ?        S    01\:35   0:00 /usr/sbin/httpd -k start
 # tail /var/log/apache2/error_log
 [Mon Jun 27 11:08:11.883571 2022] [proxy_fcgi:error] [pid 1135417] [client 10.3.4.18:60147] AH01071: Got error 'Primary script unknown', referer: https://adam.university.cpanel.net/cpanelid.html
 [Mon Jun 27 11:09:41.352206 2022] [proxy_fcgi:error] [pid 1135238] [client 10.3.4.18:60555] AH01071: Got error 'Primary script unknown'
 [Mon Jun 27 14:08:13.091321 2022] [proxy_fcgi:error] [pid 1135238] [client 10.0.48.48:41834] AH01071: Got error 'Primary script unknown'
 [Mon Jun 27 14:08:13.091888 2022] [proxy_fcgi:error] [pid 1138150] [client 10.0.48.48:41838] AH01071: Got error 'Primary script unknown'
 [Mon Jun 27 14:08:13.121549 2022] [proxy_fcgi:error] [pid 952740] [client 10.0.48.48:41846] AH01071: Got error 'Primary script unknown'
 [Mon Jun 27 14:08:13.126039 2022] [proxy_fcgi:error] [pid 952739] [client 10.0.48.48:41852] AH01071: Got error 'Primary script unknown'
 [Mon Jun 27 22:26:19.176658 2022] [mpm_prefork:notice] [pid 952735] AH00171: Graceful restart requested, doing restart
 [Mon Jun 27 22:26:19.390095 2022] [:notice] [pid 952735] mod_ruid2/0.9.8 enabled
 [Mon Jun 27 22:26:19.392739 2022] [mpm_prefork:notice] [pid 952735] AH00163: Apache/2.4.54 (cPanel) OpenSSL/1.1.1k mod_bwlimited/1.4 configured -- resuming normal operations
 [Mon Jun 27 22:26:19.392758 2022] [core:notice] [pid 952735] AH00094: Command line: '/usr/sbin/httpd'
```

Given the above information, which of the following will likely resolve the issue?

- Restart Apache with the `/scripts/restartsrv_apache --hard` to force restart all Apache children.

---

You receive a few tickets from your clients stating that their websites are down. Upon checking the Service Status feature in WHM, you notice Apache is down and try to restart the service in WHM. The interface displays the following message:
```
Apache Restart Output: Apache could not be started due to an error: The “/usr/local/cpanel/scripts/restartsrv_httpd --start” command (process 3210) reported error number 255 when it ended. Waiting for “httpd” to start ………
```
To view any potential errors that are being produced from the service restart, you head to the command line and run the restart script:
```
# /scripts/restartsrv_httpd
 [...]
 Log Messages
 Feb 14 06:29:33 acit-iftv-webhost systemd: Failed to start Apache web server managed by cPanel EasyApache.
 Feb 14 06:29:33 acit-iftv-webhost restartsrv_httpd: httpd: Syntax error on line 273 of /etc/apache2/conf/httpd.conf: Syntax error on line 33 of /etc/apache2/conf.d/modsec2.conf: Syntax error on line 27 of /etc/apache2/conf.d/modsec/modsec2.cpanel.conf: Could not open configuration file /etc/apache2/conf.d/modsec_vendor_configs/OWASP3/crs-setup.conf: No such file or directory
 [Mon Feb 14 06:05:28.250460 2022] [:error] [pid 906] [client 10.0.0.5:59258] [client 10.0.0.5] ModSecurity: Warning. Operator GE matched 5 at TX:inbound_anomaly_score. [file "/etc/apache2/conf.d/modsec_vendor_configs/OWASP3/rules/RESPONSE-980-CORRELATION.conf"] [line "91"] [id "980130"] [msg "Inbound Anomaly Score Exceeded (Total Inbound Score: 8 - SQLI=0,XSS=0,RFI=0,LFI=5,RCE=0,PHPI=0,HTTP=0,SESS=0): individual paranoia level scores: 8, 0, 0, 0"] [ver "OWASP_CRS/3.3.2"] [tag "event-correlation"] [hostname "10.0.0.100"] [uri "/403.shtml"] [unique_id "YgnxKBD_ghLEXXyhIwo-vAAAAA0"]
 [Mon Feb 14 06:05:28.249086 2022] [:error] [pid 906] [client 10.0.0.5:59258] [client 10.0.0.5] ModSecurity: Access denied with code 403 (phase 2). Operator GE matched 5 at TX:anomaly_score. [file "/etc/apache2/conf.d/modsec_vendor_configs/OWASP3/rules/REQUEST-949-BLOCKING-EVALUATION.conf"] [line "93"] [id "949110"] [msg "Inbound Anomaly Score Exceeded (Total Score: 8)"] [severity "CRITICAL"] [ver "OWASP_CRS/3.3.2"] [tag "application-multi"] [tag "language-multi"] [tag "platform-multi"] [tag "attack-generic"] [hostname "10.0.0.100"] [uri "/.env"] [unique_id "YgnxKBD_ghLEXXyhIwo-vAAAAA0"]
```

Based on the output from the script, which solution would make the most sense in the interest of getting the Apache service to start up successfully so that you can perform more diagnostics after the production environment has come back online?

- Comment out lines in `../conf.d/modsec/modsec2.cpanel.conf` that reference the non-existent file mentioned in the syntax error.

---

Your customer is reporting that their PHP application is still not reflecting those changes after making php.ini changes into a custom php.ini file that they've placed in their site's public_html folder. You do a quick check on their environment details:

```
Kernel & Architecture: 2.6.32-642.13.1.el6.x86_64
 OS: CentOS release 6.8 (Final)
 cPanel Version: 11.68.0.23
 Apache: 2.4.16, listening on ports 80 & 443
 PHP: PHP 5.6.30 using DSO & mod_ruid2
 Uptime: 09:27:06 up 2 days
 Load Average: 0.07, 0.07, 0.02
 Disk Usage:
 / 75% utilized
 tmpfs 0% utilized
 /boot 34% utilized
```

- The customer should use a .htaccess file instead.

---

You've been making changes to your site's PHP-FPM configuration and to the available PHP extensions to improve security, and all of a sudden, your site stops working. You've made so many changes between the last check of your site and now that you aren't sure which change is causing the issue. You check the site's PHP error log and find the following:

```
[15-Aug-2022 18:51:17 UTC] PHP Fatal error:  Uncaught Error: Call to undefined function define() in /home/pandaham/public_html/index.php:14
```
Based on the above error, what can you reasonably conclude is causing the issue?

- The `define` function is included in the `disable_functions` setting.

---

What is the Apache configuration directive specifies the folder location from which a VirtualHost's static files are served?

- <Directory

---

You've found your next support ticket to work on, and the customer's site, coolsite.com, is displaying a "Forbidden" error message instead of the actual site content. Thinking about the troubleshooting process, you decide to start with Apache to rule out any issues. You're in luck! You see the following log entry when attempting to access the customer's site:

```
[Mon Aug 15 18:08:02.788211 2022] [core:crit] [pid 1244644] (13)Permission denied: [client 162.158.62.196:0] AH00529: /home/coolsite/public_html/.htaccess pcfg_openfile: unable to check htaccess file, ensure it is readable and that '/home/coolsite/public_html/' is executable, referer: https://coolsite.com/
```

There is nothing wrong with the htaccess file's permissions or ownerships, yet the site still isn't loading correctly. You decide to check the full path leading up to htaccess file to rule out any other permission or ownership problems:

```
f: /home/coolsite/public_html/.htaccess
dr-xr-xr-x  root      root      /
drwx--x--x  root      root      home
drwx--x--x  coolsite  coolsite  coolsite
drw-rw-rw-  coolsite  coolsite  public_html
-rw-r--r--  coolsite  coolsite  .htaccess
```

Based on the above output, what can you reasonably conclude as the cause of the error?

- The documentroot's group needs to be changed to `nobody`.

---

When operating within a cPanel & WHM environment, which of these commands would display all available EasyApache 4 packages from within the server's command line?

- yum list "ea-*"

---

In a cPanel & WHM environment, within which of the following paths would you be able to find the Apache modules stored?

- /etc/apache2/modules/

---

In a cPanel & WHM environment, which of the following options describes a method you can use to change Apache's MPM from the command-line?

- The "yum shell" command should be used to perform a batch transaction so that your web content does not produce errors.

---

In a cPanel & WHM environment, if you select PHP 5.6 as the default PHP version, then from which of the following paths will the php.ini file be loaded?

- /opt/cpanel/ea-php56/root/etc/php.ini

---

Which of the following terms can be described as a special text string syntax used for describing a search pattern?

- Regular Expression

---

When administering a server running cPanel & WHM, which of the following commands contains the appropriate paths and arguments needed to install an EasyApache 4 profile from the command-line?

- /usr/local/bin/ea_install_profile --install /etc/cpanel/ea4/profiles/cpanel/default.json

---

Which of the following command-line utilities can best be described as a tool that allows you to concurrently install multiple versions of the same component (software collections) onto your system, and is often used with EasyApache 4/MultiPHP operations?

- scl

---

How does the /usr/local/bin/php executable know which version of PHP it should be using?

- The system's default PHP version is always used.

---

Referencing the Apache error log entry shown below, which of the following options best describes the yellow-highlighted portion of the log entry (take note of the specifically-highlighted word)?

```
[Fri Sep 09 10:42:29.902022 2011] [core:error] [pid 35708:tid 4328636416] [client 72.15.99.187] File does not exist: /usr/local/apache2/htdocs/favicon.ico
```

- The name of the Apache module that triggered the error.

---

In a cPanel & WHM environment, which of the following paths contain each installed version's PHP configuration files (php.ini), used by MultiPHP? ("##" representing the PHP version, in the options below)

- /opt/cpanel/ea-php##

---

Which of the following yum commands would remove, or uninstall, the mod_speling RPM?

- yum remove ea-apache24-mod_speling

---

Which of the following options indicates the HTTP status code that results in the status message shown below?

OK. The request was successful.

- 200

---

When an EasyApache 4 profile is uploaded through the WHM interface, where within the file system is it stored?

- /etc/cpanel/ea4/profiles/custom

---

Which of the following components can be described as a specific SAPI that provides functionality in a module that behaves as if it had been compiled into Apache itself, handling appropriate requests without producing new, non-Apache processes?

- DSO

---

Which of the following options indicates the HTTP status code that produces an error like the one shown below?

Forbidden. Access was denied to at least one relevant file.

- 403

---

Which of the following options describes the best way for you to enable the experimental repository for EasyApache 4, when operating within a cPanel & WHM environment?

- Perform the following command from the command-line, as root or equivalent: yum install ea4-experimental

---

If a user wants to utilize the system default version of PHP, which of the following selections would they enable for their account?

- inherit

---

In modern installations of cPanel & WHM, EasyApache 4 will allow you to install which of the following versions of Apache?

- Apache 2.4

---

Which of the following options accurately describe an action that one can perform from within WHM's EasyApache 4 interface?”

- Change the php.ini files that are utilized for each installed PHP version.

---

Which of the following options best describes the method you would use to install the PHP-FPM software, within a cPanel & WHM environment?

- PHP-FPM appears under the PHP Extensions stage of the EasyApache 4 profile customization walkthrough.

---

In modern installations of cPanel & WHM, when selecting DSO from the EasyApache 4 interface without mod_ruid2 or mpm_itk, what recommendation will be displayed to you automatically, directly from within the EasyApache 4 interface?

- PHP DSO runs as the nobody user by default. In a shared hosting environment, this is a security issue.

---

Which of the following options best describes the procedure needed to enable the BlueHost SymLink Protection Patch?

- Toggle the corresponding option found in WHM's Apache Configuration's Global Configuration interface.


---

In modern installations of cPanel & WHM, which of the following PHP configuration values are set automatically during the Initial Setup Assistant steps?

- memory_limit

---

Which of the following accurately indicates the user that processes created for the DSO handler are owned by?

- nobody user

---

Of the following options, which of these handlers operate in a non-persistent state, requiring the creation of new PHP processes each time something is executed?

- suPHP

---

In modern installations of cPanel & WHM, how is the PHP version determined for newly created accounts, when System PHP-FPM status is set to ON?

- It is set to the same value as the system default.

---

Which of the following options is NOT a real Multi-Processing Module (MPM) available for installation within WHM's EasyApache 4 interface?

- Postfork

---

Which of the following options describes an action that can be performed from within WHM's MultiPHP Manager interface?

- You can turn on PHP-FPM, per-virtual host, from this interface.

---

Which of the following options accurately describes an action one performs in WHM's EasyApache 4 interface?”

- Install new PHP extensions for use in your active Apache/PHP environment.

---

Given the following options, select the components or component combinations that would provide standard per-user process ownership for handling PHP content.

- suPHP (mod_suphp) OR Ruid2 (mod_ruid2) OR PHP-FPM

---

Which of the following options describes the appropriate method needed to enable PHP-FPM from within the WHM interface?

- PHP-FPM is enabled via WHM's MultiPHP Manager interface.

---

## Domain Name Server (DNS) Administration

Which of the following statements best describes the term resolver?

- A nameserver that can resolve non-local domains.


---

Which of the following best describes one of the primary, intended purposes of a DNSOnly server?

- Providing a means of establishing DNS redundancy in a cluster configuration.

---

By default, cPanel creates SPF records in which of the following modes?

- Development mode (non-production)

---

Which of the following options most accurately describes the interface or interfaces that you would utilize to create reverse DNS zones from within WHM?

- This cannot be done in WHM.

---

Which of the following most accurately describes what happens when a zone contains two CNAME records with the same name?

- The zone is considered invalid.


---

After installing cPanel & WHM in a new environment, what is the initial, default state of DNS clustering?

- DNS clustering is initially disabled and requires validation of a secondary server before allowing you to enable it.

---

The following options found in the Exim Configuration Manager - Basic Editor interface in WHM enables the checking of DNS resolution to see if the sender's domain exists?

- Sender Verification Callouts

---

Which of the following options indicates what the abbreviation TTL stands for, in the context of DNS?

- Time To Live; indicating how long a resource record should be cached.

---

In which of the following WHM interfaces would you enter the default nameservers for accounts that root creates?

- WHM Home >> Server Configuration >> Basic WebHost Manager Setup

---

Which of the following types of DNS cluster synchronization found in WHM can be best described as the copying of one updated zone file to the current server, based on the value you provide as the domain you wish to synchronize?

- Synchronize one zone to this server only.


---

Diego is a web designer who operates his own cPanel & WHM server. He wants to create a test subdomain for one of his clients and upload some web content to it so that he can share a "beta" (non-production) version of the site to his client.

Which of the following interfaces should he start with, in order to accomplish this?

- cPanel » Domains » Subdomains

---

Which of the following described situations would utilize DNS resolution as a key component of its handling?

- To determine where to send mail for a domain.

---

Yudith runs a small web-hosting company.  She has added and removed several zones manually but has accidentally deleted a zone belonging to a cPanel account. Fortunately, this zone did not contain any custom records.

Given the situation, which of the following WHM interfaces should she utilize to re-create the zone?

- WHM » DNS Functions » Add a DNS Zone.

---

Which of the following DNS clustering synchronization types, found in the WHM interface, can be best described as the copying of all updated versions of local zone files to all servers in the cluster?

- Synchronize all zones to all servers.

---

Which of the following statements most accurately describes the term clustering, in the context of a server hosting environment?

- Two or more servers that all serve the same purpose configured in a distributed, connected environment.

---

Given the following options, which indicates the ideal source from which you should obtain your server's resolver IP addresses?

- Your hosting provider or data center.

---

Which of the following types of DNS cluster synchronization found in the WHM interface can be accurately described as the copying of all updated versions of local zone files from other servers in the cluster to this server?

- Synchronize all zones to this server only.

---

When you use the supported 1:1 NAT setup in WHM, the List Accounts interface in WHM will display which of the following values in each accounts' listed IP address column?

- The public IP address.

---
Which of the following options best describes the term recursive, in the context of DNS?

- A recursive nameserver can resolve non-local domains.

---

Which of the following most accurately describes what happens when a domain with two NS records in its zone is queried?

- Both records are returned.

---

In a BIND/named configuration file, which of these logging categories encompasses all categories that have not already been explicitly configured to use another channel?

- default

---

By default, which of the following sections appear first in the named.conf file?


- key

---

What does the acronym TLD represent, as in for a "TLD nameserver"?

- Top-level Domain

---

In a cPanel & WHM environment, DNS zone templates can be used to ensure which of the following?

- To standardize a set of zone records and structure that will be used for a large number of DNS zones.

---

Which section of the named.conf file controls BIND/named's listening port?

- options

---

Which of the following utilities included with BIND/named can be used to troubleshoot malformed zone files?

- named-checkzone

---

To retrieve the IPv6 record of a domain, you would query for which of the following records in a domain?

- AAAA

---

After you update a zone's serial number (or any other record), which of the following commands can you execute to ensure that your local nameserver has been updated to use the new zone data?

- rndc reload

---

Which important configuration file would allow you to change important server options, such as enabling debug logging for BIND/named?

- /etc/named.conf

---

In a cPanel & WHM server, which of the following would allow you to select another DNS server application from the command line?

- setupnameserver

---

On a cPanel & WHM environment, the system stores the private/public keys for DKIM in which of the following paths?

- /var/cpanel/domain_keys

---

To force the local system to resolve a domain to a specific IP address, which of the following files would you modify to accomplish this?

- /etc/hosts

---

When you see a "rndc reload: connection refused" error, which of the following commands should you run first?

- /scripts/fixrndc

---

Which of the following nameserver applications does not load all of its DNS zones upon startup?

- MyDNS

---

Which of the following utilities can be used to administer a BIND/named server remotely?

- rndc

---

Which of the following is the first nameserver that the resolver queries to determine the address of the TLD nameserver?

- The root nameserver.

---

Which of the following DNS-related command-line utilities would provide you with similar results to those given by the dig utility, and is used for essentially the same purposes?

- nslookup

---

On a server that does not need to facilitate zone transfers, which of the following configuration variables found in the named.conf file should be set to none to disable them?

- allow-transfer


---

A default cPanel & WHM environment configures a custom logging channel, default_log, to log to which of the following paths?

- /var/log/named/named.log

---

By default, which of these logging categories are routed into the default_log channel, in a BIND/named DNS server configuration?

- general

---

## Database Server Administration

Which of the following MySQL/MariaDB-related terms describe a data structure that improves operations' speed in a table accurately?

- Index

---

Which of the following actions can you perform directly from within the WHM interface, without using phpMyAdmin?


- Change a database user's password.


---

What language is used to add, remove, and view data in a MySQL/MariaDB database?

- SQL

---

Which of the following is a term that indicates a trait of the object described by the table, or can be otherwise referenced as a table column?

- Field

---

Which of the following best describes the MySQL root password's role in a cPanel & WHM environment?

- A password that is primarily handled via automated means by cPanel & WHM back-end services and can be reset as needed.


---

Which of the following details about the remote server would you need to know, if you wanted to set up a new remote MySQL profile in WHM?


- Remote MySQL listening port

---

The WHM Home >> SQL Services >> Additional Access Hosts interface creates server-level grants that are similar to the grants that can be created in which of the following cPanel account-level Interfaces? 

- cPanel Home >> Databases >> Remote MySQL

---

Given the following options, which accurately describe a feature specific to the MyISAM storage engine?

- MyISAM has repair capabilities that allow you to perform the REPAIR query, either directly or from the WHM interface, on tables that may have corrupted data or indexes.

---

Which of the following is one of the most common causes of MySQL upgrade failures? 

- Aborting the upgrade, intentionally or otherwise, part-way through the procedure.

---

Ananya has a website that writes data into a MySQL database. She was mail-bombed, and as a result, has gone over the quota that was set for her account by the WHM server administrator. Which of the following best describes what happens to her website now?

- It continues operating normally and no production impact is seen.

---

When using a cPanel & WHM environment, remote MySQL capabilities should be set up via the MySQL Profiles interface in WHM at which of the following stages of a server's operations?

- After installation, but before beginning to create production accounts on the server.


---

The WHM Home >> SQL Services >> Manage Databases interface allows you to do which of the following operations?

- Automate renaming of a MySQL/MariaDB database.

---

Which of the following terms can be described as the way that permissions are handled inside a MySQL or MariaDB database?


- Grants

---

In modern versions of cPanel & WHM, what benefits can database prefixing, enabled from the SQL tab of the Tweak Settings interface in WHM, provide?


- Primarily cosmetic; helps server administrators identify database ownership, as well as providing auto-grouping in the phpMyAdmin interface.

---
Which of the following database-related terms defines marking a table or row so that only one process can access it a time?”

- Locking

---

Which of the following definitions best describes InnoDB's data dictionary component?

- A part of the InnoDB storage engine that uses metadata to map structural information to the file it’s stored in.

---

Which of the following types of tables can you repair using the Repair a MySQL Database interface, found in WHM?

- MyISAM

---

Which of the following options describes an actual benefit of utilizing remote MySQL capabilities using the MySQL Profiles feature in WHM?

- Remote MySQL servers can reduce load on the WHM Server.

---

Using the Manage MySQL Profiles interface in WHM, what is the recommended maximum number of cPanel & WHM servers should be connected to each configured remote MySQL server?

- 1

---

By default, what kind of remote MySQL access is allowed, given the correct user and password?

- No remote access is provided by default.

---

From the command line in a cPanel & WHM environment, how could you determine whether a server is utilizing a remote MySQL server?

- Check /root/.my.cnf for a “host” line.

---

In a cPanel & WHM environment, which of the following tools can best be described as the executable that creates grants_[cpuser].yaml files from existing MySQL grants, as found within the existing mysql.user database?

- restoregrants

---

When should you make backups of your configuration files (or the my.cnf file in particular)?

- When changes are made to the configuration.

---

Which of the following SQL queries would be the most effective in identifying MySQL users that still have pre-4.1 passwords in use?

- SELECT DISTINCT user FROM user WHERE length(password) < 41;


---

In a cPanel & WHM environment, which of the following tools can be best described as the executable that reads the grants_cpuser.yaml file, then adds the corresponding grants to MySQL.


- restoregrants

---

Which of the following statements is not a legitimate SQL statement?

- COPY

---

The following text shows an example of which type of syntax, also visible in some mapping-related files stored by cPanel within the file system?

- JSON

---

In a cPanel & WHM environment, which of the following describes the purpose of the files that exist within the /var/cpanel/databases directory?

- To store mapping information to help store data regarding association between cPanel accounts and databases.

---

Which of the following describes one of the important steps discussed when describing how a full MySQL data directory can be manually restored from a cPanel-created backup?


- Ensure ownership of the restored files is mysql:mysql, after being copied into the data directory.

---

In a cPanel & WHM environment, the /var/cpanel/databases directory contains which of the following?

- The files created and used by cPanel for database mapping.

---

You must stop the MySQL service in order to perform which of the following actions? 

- Relocate or rename the data directory file in the MySQL data directory.

---

Within which of the following locations could you check if you wanted to confirm whether a cPanel & WHM server has "old (pre-4.1) passwords" enabled?

- Tweak Settings interface in WHM.

---

When looking at the following excerpt from the beginning of a SHOW GRANTS result, what does the term USAGE ON indicate on the *.* value that follows?

GRANT USAGE ON *.*

- That no privileges are given.

---

Which of the following file extensions are associated specifically with InnoDB tables?


- ibd

---

Which of the following MySQL/MariaDB-related variables can be controlled via an option found within WHM's Tweak Setting interface?

- max_allowed_packet

---

How can you prevent cPanel & WHM from performing automated updates on the MySQL® or MariaDB server software?

- By using the update_local_rpm_version script.

---

Error messages in your database error logs that indicate invalid, missing or unexpected system tables can frequently be the result of which of the following issues?

- An incomplete (partial) upgrade.

---

If the MySQL processes are stopped using the kill -9 command, what can you expect to happen?

- An increased security risk of compromised authentication.

---

Which of the following can be described as a calculated numerical value resulting from a pre-determined algorithm used to represent a set of data?

- Bitwise operator

---

Which of the following MySQL/MariaDB-related variables can be controlled via an option found within WHM's Tweak Setting interface?

- open_files_limit

---

## Mail Server Administration

Which of the following options best describes what is indicated by the act of a mail server "relaying" its mail?

- It is handing mail off to another mail server for delivery.

---

In which WHM interface can you configure the forwarders for the root, cPanel, and nobody mail accounts?

- WHM Home » Server Contacts » Edit System Mail Preferences

---

Which of the following options describe an actual value that can be adjusted within the WHM Home » Service Configuration » Mailserver Configuration interface?

- Controlling the maximum and spare quantities of authentication daemon processes.

---

SCENARIO: You receive a report that all mail from a specific user on your server is neither delivered to the inbox nor bounced.

When you check the WHM Home » Email » Mail Delivery Reports interface, you see a green checkmark icon next to the message. Which of the following options best describes what this may indicate? 

- That the message was delivered successfully to a folder other than the inbox.

---

Given the following, which best describes an actual reason that the system may place a message into the Exim queue?

- The load average on the server is above the delivery threshold.

---

Which of the following options describes one of the commonly known characteristics, though are not always indicative, of an average spam email message?

- The message has a "Reply-to" address defined.

---

 The following items from the WHM Home » Service Configuration » Exim Configuration Manager - Basic Editor interface would allow you to exclude mail sent from specific remote IP addresses or hostnames from being subjected to recipient verification checks, sender checks, spam checks, and relay checks?

- Trusted SMTP IP Addresses

---

You can use the Exim Configuration Manager - Basic Editor to configure Exim to deliver mail without scanning messages based on which of the following criteria?

- When the message is over a certain size.

---

Given the following options, which accurately describe the Mail Troubleshooter interface's behavior, found in WHM?

- It does not send an actual test message but simulates sending one.

---

When mail is delivered to "/dev/null”, which of the following statements accurately indicate what happens to the message?

- The message has been permanently deleted.

----

Given the following options, which best describes something about an email address that can be determined by using the WHM Home » Email » Mail Troubleshooter interface, found in WHM?

- It will indicate whether the destination address forwards mail to a remote server.

---

Which of the following tools may help you to resolve issues indicated by the time moved backwards warning?

- The "Sync Time" tool in WHM »Server Configuration » Server Time

---

What actions can you perform in the WHM Home » Email » Mail Queue Manager interface?”

- Delete a particular message permanently so that is not delivered.

---

Justine's boss just told her that the authentication daemon for the mail server is broken.  Which of the following options best indicates the component of the mail system that is affected by this?

- The component that validates user credentials.

---

All mail from a specific user is neither delivered to the inbox nor bounced. When you check the WHM Home » Email » Mail Delivery Reports interface, you see a funnel-shaped icon next to the message.

Which of the following options best describes what this probably indicates?

- The message was likely rejected at SMTP-time due to spam-like characteristics.

---

If there is a long delay indicated when an email is being sent, the Mailer Daemon will send a warning message to which of the following destinations?

- The email's sender.

---

Given the following, which option best describes an actual reason that the system may place a message into the Exim queue?

- There are DNS issues preventing Exim from finding the remote mail server.

---

cPanel & WHM allows you to choose whether mail should be held in the queue or returned to sender when the recipient's mailbox meets which of the following criteria?

- Exceeds its assigned quota.

---

Which of the following options accurately describes the behavior of an open relay server?

- An open relay server does not require you to authenticate.

---

Which of the following Mail interfaces in WHM can provide you with a historical snapshot of the mail queue?

- Mail Delivery Reports

---

Which of the following commands will remove all messages sent by the spammer@example.tld user within the last 30 minutes?

- exiqgrep -f spammer@example.tld -y 1800 -i | xargs exim -Mrm

---

Which of the following can be discerned from the Exim log entry shown below?

```
1YO6VR-00081w-7C => test <test@cpanel.net> R=virtual_user T=virtual_userdelivery
```

- The message was delivered

---

What is the role of the -y flag when used with the exiqgrep utility?

- Messages older than the number of seconds given.

----

Of the following mailbox formats, which of these are supported for use in cPanel & WHM environments?

- mdbox

---

Which of the following can be discerned from the Exim log entry shown below?

```
1YO6bD-000871-1j => /dev/null R=virtual_user_filter T=**bypassed**
```

- The message was deleted

---

Of the following mailbox formats, which of these are supported for use in cPanel & WHM environments?

- MailDir

---

Which of the following describes what is indicated by the use of the virtual_user router during a message's delivery, as seen in the exim logs?

- The message was delivered to an email account created in the cPanel interface.

---

Which of the following values are provided in the output of the exim -bp command?

- Exim ID

---

Which of the following best describes the role of the exim -bpc command?

- Prints the number of messages in the mail queue.

---

Prints the number of messages in the mail queue.

```
2015-02-18 09:25:42 1Y06VR-0000Iw-7C= test@cptest.test H=localhost ([10.5.2.154]) [::1]:38793 P=esmtpa A=dovecot_login:test@cptest.test S=724 id=afc7s4294172a42cd5ce527636d7b74c.squrrel@10.6.2.152 T="test discard filter" for filters@cptest.test
```

- The Exim ID

---

Which of the following Actions in a cPanel email filter will result in an incoming message being rejected without sending any notifications?

- Discard Message

---

Which of the following describes the primary role of the exim -Mvb command?

- Prints the message body when given the Exim ID.

---

Given the following options, which one would be descriptive of behavior most likely to indicate that a spam problem is occurring?

- A large number of failed messages reported

---

Which of the following exim commands would output the number of messages that currently exist in the Exim mail queue?

- exim -bp

---

Which of the following describes what is indicated by the use of the localuser router during a message's delivery, as seen in the Exim logs?

- The message was delivered to a default (cPanel) account.

---

When using Maildir, the "cur" folder contains which of the following items?

- Mail that HAS been read.

---

A particular type of email filter is stored in the /etc/vfilters/ directory. Which of the following types of filters are these?

- Account-level email filters.

---- 

On cPanel & WHM environments, inbound mail is stored within a subfolder structure that exists in which of the following directories?

- /home/$USER/mail/

---

Which of the following Exim log entries would indicate that mail was deleted due to a filter?

- 1YO6bD-000871-1j => /dev/null <test@cptest.test> R=virtual_user_filter T=**bypassed**

---- 

Given two cPanel servers exchanging email, which of the following would appear in both messages' headers, but would not appear in the Exim logs on either the sending or the receiving server?

- Exim ID

---

## Development for cPanel & WHM

Which API allows you to manage cPanel licenses?

- Manage2 API

---

Which file contains the settings for a plugin?

- Configuration

---

Which term is defined as: "modifies an interface’s features or functionality, and it may also include changes to the interface’s appearance."?

- plugin

---

The ea-cpanel-tools package contains executables to help you manage your EasyApache 4 configurations from the command line are found in this location:

- /usr/local/bin

---

What of the following can be described as a structured way for one program to offer services to other programs?

- API

---

Webmail plugins are available to which type of accounts?

- Mail user

---

An example of an API could be seen as which of the following situations?

- Acquire a list of databases

---

Which language is used for a plugin installation?

- Perl

---

What is the purpose of the template file in a Plugin?

- Displays UI content

---

cPanel plugins are available to which type of accounts?

- Root

---

Which is the primary API that is used to modify cPanel user data?

- UAPI

---

Which API performs server-level tasks?

- WHM API 1

---

All of the following are features of the developer license except …

- production accounts are forbidden

---

While not advised, which port would you use for unsecured API calls to a specific cPanel account?

- 2082

---

WHM plugins MAY BE available to which types of accounts?

- Root or Reseller

---

To register a hookable event which script would you run?

- /usr/local/cpanel/bin/manage_hooks

---

All of the following categories are hookable events except …

- Update

---

To enable debug mode you would do which of these actions?

- Choose the option from the Tweak Settings interface.

---

All of the following types of code can be used as a hook action code are permissible except …

- .exe

---

All of the following code types can be run as a hook except …

- NodeJS

---

How many categories of hookable events are possible?

- 8

---

The script that you need to use to “register” your standard hook is called …

- register_hooks

---

Hook action code must be treated as an encoded data structure of which of the following types?

- JSON

---

All of the following stages can be hooked during a backup except …

- post

---

All hook action scripts must have the correct file permissions to work properly, which permissions do they need to have?

- 755

---

The location of the branding files for root is found in which of these locations?

- /var/cpanel/customizations/brand

---

Which term is defined as: "Applies an overlay on the skeletal framework for all of the interfaces"?

- theme

---

When using whmapi1 on the command line and you want to perform a key/value call to the API you can specify all the following output formats except ...

- yaml ??? xml ???

---

Which of the following interfaces are you able to make branding changes to match your companies logo and brand?

- cPanel & Webmail & WHM

---

What part of an API call will specify the session of the call?

- token

---

Which language is used for a plugin installation?

- Bash

---

You would use uapi functions when you want to perform which type of operation?

- cPanel account-level operations

---

The EasyApache profiles are found in which location?

- /etc/cpanel/ea4

---

When creating a custom profile file, which file type is used to store the information?

- JSON

---

What does the alias /scripts/ point to in the file system?

- /usr/local/cpanel/bin/

---

Which term is defined as: "Adding custom content to header or footer of the UI"?

- includes

---

When a system boots, it runs a script called "onboot_handler", where are the scripts located that are run by this handler?

- /var/cpanel/on_boot/

---

The location of the branding files for resellers is found in which of these locations?

- /home/reseller/var/cpanel/reseller/brand

---

When setting "Disk Space Quota" during package creation, in which unit format must the quota be specified?

- MB

---

In order to add environment variables for your web applications, which RPM must be added?

- ea-apache24-mod_env

---
As an end user, which is the proper way to restore your full cPanel backup?

- Contact your hosting provider

---

All of the following resource limits may be set in a package except ...

- cPanel accounts

---

Let's assume a node.js developer has an account called "user" on your WHM server and they followed the cPanel guide to creating a test node.js application. Where would you find the node.js test script?

- /home/user/nodejsapp/app.js

---

All of the following external services are available for remote backup destinations except ...

- iCloud

---

A simple definition of a "package" on a WHM server would be as follows:

- a set of resource limits and list of usable features

---

During backups you need to specify staging directories, which of the following can not be used as a staging directory on your server?

- /backup

---

Which of the following can be customized in a package?

- Feature List

---

What is the version control feature provided by cPanel?

- Git™ Version Control

---

Assuming a cPanel account is using a Feature List with the "SSH Access & Terminal" feature enabled, which privilege will they need to actually access the Terminal feature?

- Shell Access

---

Which of the following git commands would you use to update the master branch?

- checkout

---

The main purpose of the application Git is?

- code version control

---

70
---

## Utilizing cPanel Support


Which of the following is one of the three types of articles you'll find within each of the parent categories of the knowledgebase?

- Questions and Answers

---

At which of the following websites can I find both knowledgebase articles written by Support analysts, as well as a means of creating cPanel support tickets as needed?

- support.cpanel.net

---

A customer is looking for articles to help walk them through the process of restricting the amount of MySQL connections per-user on their server. Which of the following article type would be most likely to assist them?

- How-Tos

---

There are two key things we recommend ensuring are present within every ticket subject, when at all possible. The first is that the subject describes the problem in short, concise words. What is the second?

- That the subject includes where the problem occurs

---

As a cPanel Support customer, we recommend that you start your visit at support.cpanel.net by performing which of the following steps?

- Search for an appropriate article, then create a ticket if none exists

---

What label is shown on the "big orange button" that directs you towards a list of categories for browsing the knowledge base articles?

- Support Topics

---

A customer is attempting to use the whmapi1 command-line tool to test some API calls on their server, before using them in their application. However, upon attempting to use this command with any API, they are receiving an error message informing them that no license exists.

Taking this scenario into account, which of the following subject titles would be most effective when creating a support ticket?

- whmapi1 always returns an error about "no license"

---

A customer is encountering an error when attempting to create an email account through the cPanel account interface on their server. Of the following options, which would make for the most effective ticket subject line?

- perl error in interface when adding email account

---

Using the following error log message as a reference point, given the following options, which would be the most effective search query for finding an article related to this specific problem?

```
info [cpwrapd] ERROR in Mysql query :(XID vwqrz2) The system received an error from the “MySQL” database “mysql”: 1819 (Your password does not satisfy the current policy requirements)
```

- Your password does not satisfy the current policy requirements

---

In our five tips for effective article searching, we recommend starting with which of the following guidelines?

- Start with a copy/paste of all relevant text.
