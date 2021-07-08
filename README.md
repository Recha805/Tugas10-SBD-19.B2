# Tugas10-SBD-19.B2
# RECHA IRFAN TRIJIANTO 311910257
# DITUGAS 10 INI SAYA AKAN MEMBACKUP DATA BASE DENGAN SQL ATAU PERINTAH DI COMMAND PROMPT.
# 1. OKE PERTAMA SAYA MEMBUKA ATAU MENJALANKAN CMD SAYA DAN MELIHAT DATABASE SAYA.
![image](https://user-images.githubusercontent.com/81579730/124904496-457ec800-e00f-11eb-8600-7948ea4cc55f.png)
# 2.LALU SAYA MENGAMBIL DATABASES YAITU "recha_311910257" DAN MELIHAT SALAH SATU TABLE ("TABLE PELANGGAN") YANG AKAN SAYA BACKUP.DAN MENJALANKAN MENGUNCI TABLE TERSEBUT DENGAN PERINTAH 'LOCK TABLE PELANGGAN WRITE'
![image](https://user-images.githubusercontent.com/81579730/124904966-bde58900-e00f-11eb-98f5-12ed5853981f.png)
# 3.SELANJUTNYA BACKUP TABLE DATABASE TERSEBUT DENGAN PERINTAH 'SELECT * INTO OUTLIFE 'b_pelanggan' FROM PELANGGAN'
![image](https://user-images.githubusercontent.com/81579730/124905255-10bf4080-e010-11eb-9919-f0c3ae585fa0.png)
# Jika proses backup berhasil maka akan muncul file backuppada direktori C:\xampp\mysql\data\recha_311910257
![image](https://user-images.githubusercontent.com/81579730/124905512-4f54fb00-e010-11eb-8652-e01ba61d870c.png)
# 4. LALU KITA MERESTORE DATA BASES KITA DENGAN PERINTAH 'LOAD DATA INFILE 'b_pelanggan' INTO TABLE PELANGGAN'
![image](https://user-images.githubusercontent.com/81579730/124905836-a064ef00-e010-11eb-9f80-5a2faeec6153.png)
![image](https://user-images.githubusercontent.com/81579730/124905847-a3f87600-e010-11eb-9a32-460ee1e0994b.png)

# OKE SELANJUTNYA MEMBACKUP DAN MERESTORE MENGGUNAKAN 'MYSQLDUMP'
# 1.Jalankan shell atau commad-prompt dan ketikkan perintah berikut untuk memulai dump database : MySQLDUMP –u root –p recha_311910257 > backup1.sql
![image](https://user-images.githubusercontent.com/81579730/124906267-15382900-e011-11eb-825b-4f31899d7fd9.png)
# Jika proses backup berhasil maka akan muncul file backuppada direktori C:\xampp\mysql\bin\backup1.sql
![image](https://user-images.githubusercontent.com/81579730/124906532-5c261e80-e011-11eb-8676-16ea6bcbf060.png)
# 2.Data yang telah di-backup dapat di restrore kembali ke dalam database dengan perintah : MySQLdump –u root –p recha_311910257 < C:\xampp\mysql\bin\backup1.sql
![image](https://user-images.githubusercontent.com/81579730/124906727-92639e00-e011-11eb-9897-c310f8ef72ac.png)

# Backup Database MySQL Otomatis dengan cronjob
# Cron adalah tool di sistem operasi berbasis UNIX (Linux, Ubuntu, dan lain-lain) yang berfungsi untuk menjalankan task atau script secara otomatis.
# Jadi untuk menjalankannya kita mendownload aplikasi cronjob terlebih dahulu.
# 1.Tulisakan script cron job untuk melakukan backup otomatis setiap hari minggu jam 12 malam.Dan ini perintahnya:
0 0 * * 7 mysqldump -u root -p recha_311910257 > backup1.sql
