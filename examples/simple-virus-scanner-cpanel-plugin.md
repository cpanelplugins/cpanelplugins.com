---
title: Specify directory root for Simple Virus Scanner
filepath: simple-virus-scanner-cpanel-plugin/index.live.php
filetype: php
order: 3
---
```php

// replace /home/f32d23/ with your root directory

public function __construct($rootFolder = __DIR__)
	{
		$this->rootFolder = ("/home/f32d23/");
