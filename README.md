# Danang-Nurcahyo-tugas-sistem-terdistribusi-

https://youtu.be/wjiD-ruFYNc?si=CrhDEyQ1BDN0FmCP 

#Langkah-Langkah Mendowload linux
Berikut langkah-langkah umum untuk menginstal dan mengkonfigurasi server DNS di Linux, menggunakan BIND sebagai contoh:

1. *Persiapkan Sistem:*
   - Pastikan sistem Linux Anda terhubung ke internet.
   - Jalankan perintah update untuk memastikan semua paket sistem terbaru:
     
     sudo apt update
     

2. *Instal BIND 9:*
   - Gunakan perintah berikut untuk menginstal BIND 9 dan utilitas terkait:
     
     sudo apt install -y bind9 bind9utils dnsutils
     

3. *Konfigurasi BIND 9:*
   - Setelah instalasi selesai, buka dan konfigurasikan file named.conf.options dan named.conf.local. Letakkan file konfigurasi ini di dalam direktori /etc/bind.
   - Anda juga perlu menambahkan zona-zona DNS yang Anda inginkan ke dalam file konfigurasi. Ini termasuk zona-zona untuk domain Anda sendiri dan mungkin zona-zona untuk domain-domain yang di-hosting oleh server Anda.

4. *Verifikasi Konfigurasi:*
   - Setelah konfigurasi selesai, jalankan perintah berikut untuk memverifikasi tidak adanya kesalahan sintaks dalam file konfigurasi BIND:
     
     sudo named-checkconf
     

5. *Mulai Layanan BIND:*
   - Setelah konfigurasi diverifikasi, mulai layanan BIND menggunakan perintah:
     
     sudo systemctl start bind9
     

6. *Uji Layanan DNS:*
   - Gunakan utilitas dig atau nslookup untuk menguji fungsi server DNS Anda. Misalnya:
     
     dig example.com
     

7. *Atur Layanan BIND untuk Memulai Secara Otomatis:*
   - Aktifkan layanan BIND agar dapat memulai otomatis setiap kali sistem di-boot:
     
     sudo systemctl enable bind9
     

8. *Monitor Log dan Pemeliharaan:*
   - Periksa log BIND untuk memastikan tidak ada masalah. Log umumnya terletak di /var/log/syslog atau /var/log/messages.

Ini adalah langkah-langkah umum untuk menginstal dan mengkonfigurasi server DNS di Linux menggunakan BIND. Pastikan untuk menyesuaikan konfigurasi sesuai dengan kebutuhan spesifik Anda.
