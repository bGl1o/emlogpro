# Emlog pro introduce

EMLOG is a lightweight open-source blog and CMS website building system that is fast, resource efficient, and easy to use, suitable for building websites of all sizes.

# The affected version

emlog pro 2.5.7

## Vulnerability description

In the emlog pro project, there is a zip file that can be uploaded at admin/views/plugin.php, and after decompression, there is no filtering or analysis of the content, so that you can upload a compressed file with php, and upload it to the server through decompression, thus getshell

Project address： https://github.com/emlog/emlog

The code audit found no filtering at the upload and decompression pointsThrough analysis, it is found that as long as the folder in the compressed package and the file name in the folder are the same  the upload can be successful thus getshell

![image-20250227205401062](https://cdn.jsdelivr.net/gh/bGl1o/Pictures@img/202502272119254.png)

![image-20250227205342537](https://cdn.jsdelivr.net/gh/bGl1o/Pictures@img/202502272120236.png)



# Vulnerablility reproduction

shell.php

```
<?php phpinfo();?>
```

Docker installation

```
docker run --name emlog-pro -p 8080:80 -d emlog/emlog:pro-latest-php7.4-apache 
```

![image-20250227205653854](https://cdn.jsdelivr.net/gh/bGl1o/Pictures@img/202502272120239.png)

![image-20250227210245816](https://cdn.jsdelivr.net/gh/bGl1o/Pictures@img/202502272120463.png)

After successful installation

![image-20250227210044174](https://cdn.jsdelivr.net/gh/bGl1o/Pictures@img/202502272120268.png)

Go to http://192.168.222.129:8080/content/plugins/shell/shell.php

![image-20250227210519989](https://cdn.jsdelivr.net/gh/bGl1o/Pictures@img/202502272120231.png)

The php file was successfully uploaded and parsed
