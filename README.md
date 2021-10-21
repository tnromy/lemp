# lemp
Tutorial cara instalasi Nginx web server, MySQL server dan PHP di ubuntu 20.04

Bekerja dengan baik di versi ubuntu yang lebih lama atau yang lebih baru.

### langkah 1: masuk ke akun super user
sudo su

### langkah 2: update daftar repository ubuntu
apt update

### langkah 3: install nginx
apt install nginx

### langkah 4: cek instalasi berhasil dengan cara membuka browser seperti google chrome & firefox, kemudian ketik ip dari komputer Anda.
### untuk cek jip komputer Anda bisa mengetik:
hostname -I

### jika instalasi nginx berhasil, maka akan terlihat halaman welcome to nginx

### langkah 5: install mysql-server
apt install mysql-server

### langkah 6: amankan instalasi mysql-server Anda dengan mengetik:
mysql_secure_installation

### jawab setiap pertanyaan untuk mengamankan database Anda

### langkah 7: isntall PHP dan depedensinya
apt install php php-fpm php-mysql

### langkah 8: cek instalasi PHP sukses dengan mengetik:
php --version

### ingant versi PHP yang terinstall karena akan digunakan pada file configurasi nginx

### langkah 9: konfigurasi nginx untuk mengenali PHP
### clone repository ini untuk mendapatkan konfigurasi default nginx PHP dengan megnetik:
git clone https://github.com/tnromy/lemp

### langkah 10: navigasi ke directory hasil clone tersebut:
cd lemp

### langkah 11: edit file nginx.conf hasil clone, sesuaikan nama domain "nocturlab.com" menjadi sesuai nama proejct Anda. Pastikan semua tulisan "nocturlab.com" diubah menjadi nama project Anda. save jika selesai.

### langkah 12: copy file nginx.conf yang telah diedit ke lokasi konfigurasi nginx:
cp nginx.conf /etc/nginx/sites-available/default

### langkah 13: restart service nginx
systemctl restart nginx

### instalasi selesai

### Anda dapat navigasi ke /var/www/:
cd /var/www/

### buat directory baru dengan nama persis seperti nama project Anda:
mkdir nocturlab.com

### Anda sudah bisa membuat file PHP di dalam directory ini. sebagai contoh buat file dengan nama index.php dan isi dengan:

<?php echo "hello world"; ?>

### reload halaman welcome nginx di browser Anda.

### Anda harus mendapatkan hasil tulisan hello world