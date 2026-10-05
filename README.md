# Laporan Praktikum 2: Perintah-Perintah Dasar Sistem Operasi Linux

**Mata Kuliah:** Sistem Operasi  
**Fakultas:** Ilmu Komputer, Universitas Sriwijaya  

---

## 📋 Deskripsi

Repository ini berisi dokumentasi pelaksanaan, pembahasan latihan, serta penyelesaian tugas praktikum secara lengkap untuk **Modul Praktikum 2: Perintah-Perintah Dasar Sistem Operasi Linux**. Praktikum ini mencakup pengenalan lingkungan Shell/CLI, utilitas identifikasi pengguna dan sistem, penggunaan manual bantuan, serta manipulasi dasar pada berkas dan direktori.

---

## 🎯 Capaian Pembelajaran (CPMK)

1. Mengenal format instruksi arsitektur sistem pada sistem operasi Linux.
2. Mempelajari utilitas dasar pada sistem operasi Linux.
3. Menggunakan perintah-perintah dasar pada sistem operasi Linux.

---

## 🛠️ Alat dan Bahan

* **Laptop / PC**
* **Virtual Machine** (VirtualBox / VMware)
* **Sistem Operasi:** Ubuntu Linux

---

## 📚 Dasar Teori & Format Instruksi

Format instruksi standar pada baris perintah (*Shell Command Line*) Linux adalah:

```bash
$ NamaInstruksi [Pilihan/Option] [Argumen]
```

* **NamaInstruksi:** Perintah dasar yang dieksekusi oleh sistem.
* **Pilihan (Option):** Opsi tambahan yang diawali dengan tanda minus (`-`) atau dua minus (`--`) untuk memodifikasi perilaku perintah.
* **Argumen:** Target operasi seperti nama file, nama direktori, atau parameter masukan lainnya.

---

## 🧪 Pembahasan Latihan Praktikum (Percobaan 1 - 15)

Berikut adalah panduan perintah dan penjelasan teknis dari setiap percobaan yang dilakukan pada praktikum:

### Percobaan 1: Melihat Identitas Diri
Menampilkan User ID (UID) dan Group ID (GID) pengguna aktif.
```bash
$ id
```
* **Penjelasan:** Perintah `id` menampilkan informasi identitas spesifik akun yang sedang digunakan, termasuk nama user, ID numerik, serta grup utama dan sekunder.

---

### Percobaan 2: Melihat Tanggal dan Kalender Sistem
```bash
# Menampilkan tanggal dan waktu sistem saat ini
$ date

# Menampilkan kalender bulan Oktober tahun 2015
$ cal 10 2015

# Menampilkan kalender penuh untuk satu tahun berjalan
$ cal -y
```

---

### Percobaan 3: Melihat Identitas Mesin / Host
```bash
# Menampilkan nama host (hostname) komputer
$ hostname

# Menampilkan nama sistem operasi
$ uname

# Menampilkan seluruh informasi detail sistem (kernel version, arsitektur CPU, dll)
$ uname -a
```

---

### Percobaan 4: Melihat User Aktif & Mengubah Informasi Finger
```bash
# Menampilkan pengguna aktif beserta aktivitasnya
$ w

# Menampilkan daftar nama pengguna yang sedang aktif
$ who

# Menampilkan nama akun pengguna saat ini
$ whoami

# Mengubah data profil/finger pengguna
$ chfn mahasiswa
```
* **Penjelasan `chfn`:** Sistem akan meminta kata sandi (*password*) lalu memberikan instruksi untuk memperbarui informasi seperti *Full Name*, *Office*, *Office Phone*, dan *Home Phone*.

---

### Percobaan 5: Menggunakan Manual (Help System)
```bash
# Menampilkan halaman manual untuk perintah ls
$ man ls

# Menampilkan halaman manual untuk perintah man itu sendiri
$ man man

# Mencari manual berdasarkan kata kunci (mirip apropos)
$ man -k file

# Menampilkan halaman manual struktur file /etc/passwd (section 5)
$ man 5 passwd
```

---

### Percobaan 6: Menghapus / Membersihkan Layar
```bash
$ clear
```
* **Penjelasan:** Membersihkan tampilan teks pada layar terminal dan menempatkan kursor kembali di sudut kiri atas.

---

### Percobaan 7: Mencari Perintah Berdasarkan Deskripsi (Kata Kunci)
```bash
$ apropos date
$ apropos mail
$ apropos telnet
```
* **Penjelasan:** `apropos` mencari kata kunci tertentu di dalam seluruh deskripsi halaman manual sistem.

---

### Percobaan 8: Mencari Perintah Spesifik
```bash
$ whatis date
```
* **Penjelasan:** `whatis` menampilkan ringkasan deskripsi satu baris mengenai fungsi suatu perintah secara persis/eksak.

---

### Percobaan 9: Manipulasi Berkas dan Direktori
```bash
# Menampilkan daftar berkas/direktori sederhana
$ ls

# Menampilkan daftar berkas/direktori format rinci (long listing)
$ ls -l

# Menampilkan seluruh berkas/direktori termasuk berkas tersembunyi (dotfiles)
$ ls -a

# Menampilkan isi direktori tanpa sorting
$ ls -f

# Menampilkan isi dari direktori /usr
$ ls /usr

# Menampilkan isi dari direktori root (/)
$ ls /

# Menampilkan isi direktori /etc dengan simbol indikator tipe (+exec, /dir, @link)
$ ls -F /etc

# Menampilkan rincian atribut seluruh file di /etc
$ ls -l /etc

# Menampilkan berkas dan isi sub-direktori secara rekursif
$ ls -R /usr
```

---

### Percobaan 10: Melihat Tipe File
```bash
# Memeriksa tipe file di direktori kerja
$ file *

# Memeriksa tipe file spesifik executable binary
$ file /bin/ls
```

---

### Percobaan 11: Menyalin (Copy) File
```bash
# Menyalin /etc/group ke file f1
$ cp /etc/group f1
$ ls -l

# Menyalin f1 ke f2 secara interaktif (meminta konfirmasi jika f2 sudah ada)
$ cp -i f1 f2

# Membuat direktori baru bernama backup
$ mkdir backup

# Menyalin file f1 ke f3
$ cp f1 f3

# Menyalin beberapa file (f1, f2, f3) sekaligus ke dalam direktori backup
$ cp f1 f2 f3 backup
$ ls backup
$ cd backup
$ ls
```

---

### Percobaan 12: Melihat Isi File
```bash
# Menampilkan seluruh isi file f1 sekaligus
$ cat f1

# Menampilkan isi file f1 secara bertahap (per halaman layar)
$ more f1
```

---

### Percobaan 13: Mengubah Nama dan Memindahkan File
```bash
# Mengubah nama file f1 menjadi prog.txt
$ mv f1 prog.txt
$ ls

# Membuat direktori mydir dan memindahkan file f1, f2, f3 ke dalamnya
$ mkdir mydir
$ mv f1 f2 f3 mydir
```

---

### Percobaan 14: Menghapus File
```bash
# Menghapus file f1
$ rm f1

# Menyalin berkas f1 & f2 dari mydir ke direktori saat ini
$ cp mydir/f1 f1
$ cp mydir/f2 f2

# Menghapus file f1 secara langsung
$ rm f1

# Menghapus file f2 secara interaktif (dengan konfirmasi)
$ rm -i f2
```

---

### Percobaan 15: Mencari Kata / Teks dalam File
```bash
# Mencari kata 'root' pada berkas /etc/passwd
$ grep root /etc/passwd

# Mencari string ID ':0:' pada berkas /etc/passwd
$ grep ":0:" /etc/passwd

# Mencari kata 'mahasiswa' pada berkas /etc/passwd
$ grep mahasiswa /etc/passwd
```

---

## 📝 Penyelesaian Tugas (Jawaban Soal Tugas VI)

Berikut adalah penyelesaian lengkap beserta analisis teknis untuk seluruh soal pada bagian **VI. Tugas**:

### 1. Mengubah Informasi Finger Komputer

**Perintah:**
```bash
chfn mahasiswa
```

**Langkah & Hasil Eksekusi Terminal:**
```text
Changing finger information for mahasiswa.
Password: [masukkan_password_user]
Name [Student]: Ahmad Syahputra
Office [ ]: Lab Jaringan dan Sistem
Office Phone [ ]: 0711-580012
Home Phone [ ]: 081234567890

Finger information changed.
```

**Verifikasi:**
Untuk memastikan bahwa informasi *finger* berhasil diperbarui, jalankan perintah:
```bash
getent passwd mahasiswa
```
*Output Verifikasi:*
```text
mahasiswa:x:1000:1000:Ahmad Syahputra,Lab Jaringan dan Sistem,0711-580012,081234567890:/home/mahasiswa:/bin/bash
```

---

### 2. Melihat Log User-User yang Sedang Aktif

Untuk melihat daftar pengguna yang sedang aktif di sistem komputer, dapat dilakukan dengan tiga variasi perintah berikut:

**Perintah 1:**
```bash
who
```
*Output Contoh:*
```text
mahasiswa tty1         2026-10-05 07:30
mahasiswa pts/0        2026-10-05 08:15 (:0)
```

**Perintah 2:**
```bash
w
```
*Output Contoh:*
```text
 08:30:00 up 1:00,  2 users,  load average: 0.08, 0.04, 0.01
USER     TTY      FROM             LOGIN@   IDLE   JCPU   PCPU WHAT
mahasis  tty1     -                07:30    1:00m  0.03s  0.03s -bash
mahasis  pts/0    192.168.1.15     08:15    0.00s  0.12s  0.02s w
```

**Perintah 3:**
```bash
whoami
```
*Output Contoh:*
```text
mahasiswa
```

**Penjelasan:**
* `who`: Menampilkan nama pengguna, nama terminal (`tty` atau `pts`), serta waktu login.
* `w`: Menampilkan daftar pengguna aktif beserta statistik beban sistem (*load average*) dan proses/perintah yang sedang dieksekusi masing-masing user.
* `whoami`: Mengembalikan identitas nama pengguna tunggal yang sedang mengendalikan terminal saat ini.

---

### 3. Analisis Berkas `/etc/group` untuk Baris `root:x:0:`

**Perintah:**
```bash
cat /etc/group | grep root
# Atau perintah alternatif:
grep "root" /etc/group
```

**Hasil Output Perintah:**
```text
root:x:0:
```

**Analisis Terperinci Sintaks `root:x:0:`:**
Baris pada berkas `/etc/group` dibagi menjadi 4 bidang (*field*) utama yang dipisahkan oleh tanda titik dua (`:`):

| No | Bidang (*Field*) | Nilai | Analisis & Deskripsi |
| :---: | :--- | :---: | :--- |
| **1** | **Group Name** | `root` | Nama dari grup administratif tertinggi di dalam sistem Linux. |
| **2** | **Group Password** | `x` | Menunjukkan bahwa kata sandi grup disimpan secara terenkripsi di dalam berkas terpisah yang lebih aman, yaitu `/etc/gshadow`. |
| **3** | **Group ID (GID)** | `0` | Angka **0** merupakan *Group ID* (GID) khusus milik superuser/root. Seluruh akun yang memiliki akses ke GID ini memiliki hak akses administratif penuh. |
| **4** | **User List** | *(Kosong)* | Bidang ini memuat daftar anggota tambahan grup. Kosong menandakan pengguna `root` secara *default* sudah merupakan pemilik utama grup ini tanpa perlu mencantumkannya lagi. |

---

## 📌 Kesimpulan

Berdasarkan seluruh rangkaian percobaan dan latihan pada Praktikum 2 ini, dapat disimpulkan bahwa:

1. Antarmuka baris perintah (*Command Line Interface / CLI*) Linux memfasilitasi manajemen sistem operasi secara fleksibel melalui perintah yang terstruktur (*Perintah - Opsi - Argumen*).
2. Perintah seperti `id`, `who`, `w`, dan `chfn` membantu administrator untuk mengidentifikasi dan mengelola profil akun pengguna di dalam sistem.
3. Struktur sistem berkas Linux sangat bergantung pada utilitas dasar seperti `ls`, `cp`, `mv`, `rm`, dan `file` untuk manipulasi data secara efisien.
4. File konfigurasi seperti `/etc/passwd` dan `/etc/group` menyimpan struktur fundamental identitas dan hak akses kelompok pengguna (*groups*) pada sistem Linux.
