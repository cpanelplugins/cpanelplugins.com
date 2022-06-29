---
title: Add custom blacklist to RBL check cPanel plugin
filepath: rbl-check-cpanel-plugin/check.live.php 
filetype: vue
order: 1
---
```php
<?php

// Add your preferred list of DNSBL's

function dnsbllookup($ip){
        $dnsbl_lookup=array(
        "bl.spamcop.net",
        "cbl.abuseat.org",
        "dnsbl.justspam.org",
        "dnsbl.sorbs.net",
        "relays.mail-abuse.org",
        "spam.dnsbl.sorbs.net",
        "spamguard.leadmon.net",
        "zen.spamhaus.org");

```
