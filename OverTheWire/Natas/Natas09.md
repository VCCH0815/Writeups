# Natas09

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Web
**Date Completed:** 21-Oct-2026 
**Username:** natas9
**Password:** UdxmI27dTaXmnd1rxKQTfws6jihTdcQ9
**URL:** http://natas9.natas.labs.overthewire.org

---
```
<?   
$key = "";      
if(array_key_exists("needle", $_REQUEST)) 
{    
$key = $_REQUEST["needle"];   
}    
  
if($key != "") 
{    
passthru("grep -i $key dictionary.txt");   
}   
?>
```

Sourcecode shows that the script uses `passthru()` which does not sanitize. inputting `;` to allow a new command, and then `#` to comment out the rest of the grep command, I am able to cat out the password for natas10.

`; cat /etc/`
# References