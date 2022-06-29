---
title: Replace AbuseIPDB links with your own in Login Log
filepath: lastlogin-cpanel-plugin/lastlogin.live.php
filetype: js
order: 3
---
```js
<script>

// add AbuseIPDB links to the table
// to set custom links replace baseUrl
// example: https://lookup.abusix.com/search?q=


(function () {
    var table = document.getElementById('table');
    var baseUrl = 'https://www.abuseipdb.com/check/'
    for (var i = 1; i < table.rows.length; i++) {
        var firstCol = table.rows[i].cells[0]; //first column
        var curElement = firstCol;
    var parent = curElement.parentElement;
    var newAElement = document.createElement('a');
    var path = baseUrl+curElement.innerHTML;
    newAElement.setAttribute('href', path);
    newAElement.setAttribute('target', '_blank');
    newAElement.appendChild(curElement);
    parent.appendChild(newAElement)
    console.log(parent)
    }
})();
```
