---
title: Add file extensions to Malware Scanner
filepath: malware-scanner-cpanel-plugin/config.php
filetype: php
order: 2
---
```php

<?php return array (
  'file-extensions' => 'php|phtml|php3|php4|php5|phps|htaccess|txt',
  'ignored-dirs' => '.|..|.DS_Store|.svn|.git|.trash',
  'scan-dir' => '../',
  'additional-strings' => '',
); 
?>

```
