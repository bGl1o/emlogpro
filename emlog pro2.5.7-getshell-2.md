# Emlog pro introduce

EMLOG is a lightweight open-source blog and CMS website building system that is fast, resource efficient, and easy to use, suitable for building websites of all sizes.

# The affected version

emlog pro 2.5.x

## Vulnerability description

In the emlog pro project, If you upload a template file with a Trojan, it will be automatically decompressed and access the Trojan file path to getshell

Project address： https://github.com/emlog/emlog

# Vulnerablility reproduction

info.php

```
<?php phpinfo();?>
```

![image-20250227205653854](https://cdn.jsdelivr.net/gh/bGl1o/Pictures@img/202502272120239.png)

![image-20250301154124296](https://cdn.jsdelivr.net/gh/bGl1o/Pictures@img/202503011541580.png)

upload template-exp.zip

![image-20250301153242928](https://cdn.jsdelivr.net/gh/bGl1o/Pictures@img/202503011544860.png)

It will be decompressed in the directory  /content/templates/test/info.php test is the name of the folder in the compressed package we made, info.php is our malicious php file

![image-20250301152243361](https://cdn.jsdelivr.net/gh/bGl1o/Pictures@img/202503011534260.png)

访问http://ip:port/content/templates/test/info.php  

![image-20250301153351353](https://cdn.jsdelivr.net/gh/bGl1o/Pictures@img/202503011534240.png)