Kamu adalah mentor Senior DevOps / Cloud Engineer yang sedang membantu saya membuat materi belajar untuk teman saya yang sedang menjalani program 3 bulan menjadi DevOps Engineer / Cloud Engineer berbasis AWS.

Konteks:
- Teman saya sudah belajar AWS basic, Docker, CI/CD, GitHub Actions, Monitoring, dan sebentar lagi masuk Terraform + Kubernetes.
- Ternyata ada materi krusial yang tertinggal: Basic Linux Ubuntu.
- Saya ingin materi ini compact, tidak terlalu panjang, tapi padat dan benar-benar practical untuk kebutuhan DevOps/Cloud Engineer pemula.
- Output harus berupa 1 file HTML lengkap dengan CSS dan JavaScript internal.
- Materi harus mudah dipahami oleh pemula, menggunakan Bahasa Indonesia, tapi istilah teknis Linux/DevOps tetap pakai istilah aslinya jika memang umum digunakan.
- Buat tampilan modern, clean, premium, dan ada animasi ringan agar tidak membosankan.
- Jangan buat seperti artikel panjang. Buat seperti mini learning dashboard / interactive handbook.

Tujuan materi:
Membuat learner paham Linux Ubuntu basic yang paling sering dipakai DevOps/Cloud Engineer saat:
- Login ke server Ubuntu via SSH
- Navigasi folder
- Mengelola file
- Membaca log
- Mengecek service
- Mengatur permission
- Menginstall package
- Mengelola user sederhana
- Menjalankan web server
- Troubleshooting aplikasi di server

Materi wajib mencakup:

1. Kenapa Linux Penting untuk DevOps / Cloud Engineer
- Linux sebagai OS server paling umum
- Hubungan Linux dengan AWS EC2, Docker, Kubernetes, CI/CD, dan Web Server
- Mindset: jangan hafal semua command, tapi pahami pattern troubleshooting

2. Basic Terminal & Navigation
Bahas command:
- pwd
- ls
- cd
- clear
- history
- man
- whoami
- hostname
- uname -a

Berikan contoh real case:
“Setelah SSH ke EC2 Ubuntu, bagaimana tahu kita sedang ada di folder mana dan server apa?”

3. File & Directory Management
Bahas command:
- mkdir
- touch
- cp
- mv
- rm
- cat
- less
- head
- tail
- nano
- vim secara singkat saja

Tambahkan best practice:
- Hati-hati dengan rm -rf
- Gunakan ls sebelum hapus file
- Bedanya melihat isi file kecil vs besar

4. Permission & Ownership
Bahas:
- chmod
- chown
- sudo
- root vs normal user
- permission read/write/execute
- contoh chmod 755 dan 644

Buat visual sederhana di HTML:
rwx = read, write, execute

Contoh case:
“Kenapa script deploy.sh tidak bisa dijalankan?”
Solusi:
chmod +x deploy.sh

5. Package Management di Ubuntu
Bahas:
- apt update
- apt upgrade
- apt install
- apt remove
- apt search

Contoh:
install curl, git, nginx, unzip

6. Process & Resource Monitoring
Bahas:
- ps aux
- top
- htop
- free -h
- df -h
- du -sh
- uptime

Contoh case:
“Server terasa lambat, apa yang harus dicek dulu?”

7. Service Management dengan systemd
Bahas:
- systemctl status
- systemctl start
- systemctl stop
- systemctl restart
- systemctl enable
- systemctl disable

Contoh:
nginx sebagai service

8. Log & Troubleshooting
Bahas:
- journalctl
- journalctl -u nginx
- tail -f /var/log/nginx/access.log
- tail -f /var/log/nginx/error.log
- dmesg secara singkat

Contoh case:
“Website tidak bisa diakses, cek log dari mana?”

9. Networking Basic untuk DevOps
Bahas:
- ip a
- ping
- curl
- wget
- ss -tulpn
- netstat optional kalau perlu disebut legacy
- ufw status
- ufw allow 80
- ufw allow 22

Contoh case:
“Service sudah running tapi tidak bisa diakses dari browser, cek apa saja?”

10. SSH Basic
Bahas:
- ssh user@ip
- pem file concept secara singkat
- password SSH vs private key
- folder ~/.ssh
- known_hosts
- authorized_keys secara basic

Contoh:
Login ke EC2 Ubuntu via SSH.

11. Web Server Mini Module
Selipkan materi webserver yang practical:
- Apa itu web server
- Bedanya Nginx dan Apache secara singkat
- Install Nginx di Ubuntu
- Start dan enable Nginx
- Cek status Nginx
- Test via curl localhost
- Buka via browser menggunakan public IP
- Struktur folder /var/www/html
- Edit index.html sederhana
- Cek access log dan error log
- Restart Nginx setelah perubahan config

Command wajib:
sudo apt update
sudo apt install nginx -y
sudo systemctl status nginx
curl localhost
cd /var/www/html
echo "<h1>Hello from Ubuntu Server</h1>" | sudo tee index.html
sudo systemctl restart nginx
sudo tail -f /var/log/nginx/access.log
sudo tail -f /var/log/nginx/error.log

12. Mini Project Akhir
Buat mini project:
“Deploy Static Website Sederhana di Ubuntu Server”

Step:
- SSH ke server
- Update package
- Install Nginx
- Buat halaman HTML sederhana
- Pastikan port 80 dibuka
- Test via curl
- Test via browser
- Cek log akses
- Restart service
- Dokumentasikan command yang dipakai

13. Cheatsheet DevOps Linux Command
Buat tabel compact:
Kategori | Command | Fungsi | Contoh

Kategori:
- Navigation
- File
- Permission
- Package
- Service
- Logs
- Network
- Web Server

14. Troubleshooting Flow
Buat section visual seperti flowchart:
Website down?
1. Cek apakah server hidup
2. Cek SSH bisa masuk
3. Cek service nginx
4. Cek port 80 listen
5. Cek firewall
6. Cek log nginx
7. Cek disk penuh
8. Restart service jika perlu

15. Quiz Singkat
Buat 10 pertanyaan singkat pilihan ganda atau flashcard:
- Command untuk melihat disk usage?
- Command untuk melihat status nginx?
- Command untuk melihat log realtime?
- Command untuk memberi executable permission?
- Command untuk melihat port yang listening?

Requirement desain HTML:
- Single file HTML
- Responsive untuk desktop dan mobile
- Gunakan CSS internal
- Gunakan JavaScript internal
- Ada smooth animation
- Ada sidebar/table of contents
- Ada progress indicator sederhana
- Ada card untuk tiap module
- Ada command block dengan tombol copy
- Ada mini terminal simulator sederhana
- Ada accordion untuk command explanation
- Ada visual flowchart troubleshooting
- Ada quiz interaktif dengan skor
- Tampilan modern, clean, tidak default AI
- Gunakan dark mode style yang nyaman
- Warna jangan terlalu norak
- Gunakan font modern seperti Inter atau system font
- Jangan menggunakan external library/CDN agar file tetap standalone
- Boleh pakai emoji secukupnya, jangan berlebihan

Tone materi:
- Casual tapi tetap profesional
- Seperti mentor yang ngajarin langsung
- Jangan terlalu akademis
- Fokus ke “kapan command ini dipakai di real kerjaan”
- Hindari teori yang terlalu panjang
- Setiap module wajib punya:
  1. Penjelasan singkat
  2. Command penting
  3. Contoh real case
  4. Common mistake
  5. Mini practice

Output akhir:
Berikan hanya kode HTML lengkap dari <!DOCTYPE html> sampai </html>, tanpa penjelasan tambahan di luar kode.