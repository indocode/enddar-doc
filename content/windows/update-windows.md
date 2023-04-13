---
author: "Admin"
date: 2014-09-28
menu:
  main:
    parent: tutorials
next: /tutorials/github-pages-blog
prev: /tutorials/automated-deployments
title: "Update Sistem (Windows)"
weight: 10
---

{{< lead >}}

Ada banyak kendala yang dapat dihadapi setiap saat dengan menggunakan sistem dari Windows. Salah satu kesalahan adalah fitur Update Windows yang tidak dapat berjalan / selalu gagal berulang kali, dengan beberapa metode dibawah ini mungkin dapat menjadi petunjuk untuk update sistem Windows.

{{< /lead >}}



{{< panel title="CATATAN" style="info" >}}

Ada banyak kemungkinan penyebab kesalahan seperti ini. Jika Anda berurusan dengan Pembaruan Sistem yang terus gagal pada Windows versi berapapun, panduan ini agar dapat untuk memulai bisa menjadi pemecahan masalah. Untuk memulai menggunakan software **iPhone Extractor**.

{{< /panel >}}



{{< img src="/update-windows/0-windows-update-fail.png" caption="Update Windows Gagal" >}}




## Update Windows Terus Gagal

Banyak pengguna mengalami pesan kesalahan terkait dengan kegagalan Pembaruan Windows, ini termasuk pop-up kesalahan seperti **“Windows Update failed to install”** atau **“Install failed”**. Beberapa laporan pengguna ada yang tidak ada pesan kesalahan, tetapi proses pembaruan macet dan tidak berlanjut bahkan setelah beberapa waktu yang lama.


### Apa yang menyebabkan kesalahan gagal Pembaruan Windows?

Apabila ada kendala  seperti Pembaruan Windows yang gagal berulang kali, banyak hal yang mungkin dapat karena kesalahan yang berbeda-bead. Kami menyusun daftar penyebab paling umum berdasarkan informasi yang saya kumpulkan.

- **File sistem rusak atau hilang**. File sistem sangat penting untuk memastikan semuanya berfungsi di perangkat Anda. Ada kemungkinan file sistem Anda rusak atau dihapus baru-baru ini, yang menyebabkan Pembaruan Windows gagal.
- **Driver Outdate**. Driver diperlukan untuk menangani komponen yang tidak sesuai dengan kompatibilitas Windows seperti kartu grafis, kartu jaringan, dan sebagainya. Jika driver yang terkait belum diperbarui dalam beberapa saat, itu dapat menyebabkan masalah dengan Pembaruan Windows.
- **Masalah dengan layanan Pembaruan Windows**. Kemungkinan ada yang salah dengan layanan pembaruan sistem itu sendiri. Jika demikian, Anda dapat menemukan cara alternatif untuk menggunakan metode pembaruan Windows 10 terbaru di bawah ini.

Perlu diingat — daftar di atas tidak berisi semua kemungkinan penyebab. Mungkin beberapa kesalahan, karena setiap perangkat memiliki masalah yang unik (_atau tidak umum_). Namun, metode kami di bawah ini mungkin akan membantu Anda memperbaiki kesalahan dengan cara paling mudah, apa pun penyebabnya.

Jika tidak dapat memperbarui Windows karena beberapa kesalahan, jangan panik. Kendala perangkat tersebut dapat dengan mudah diperbaiki dengan mengikuti panduan terperinci di bawah ini.




### Metode 1: Jalankan alat Pemecah Masalah Pembaruan Windows

Microsoft sendiri telah mengeluarkan alat yang ditunjuk untuk membantu memperbaiki masalah dengan pembaruan Windows 10. Alat ini gratis dan tersedia untuk diunduh oleh siapa saja, bahkan tanpa Akun Microsoft. Yang harus Anda lakukan hanyalah menjalankan alat ini dan melihat apakah alat itu dapat mengidentifikasi dan memperbaiki kesalahan apa pun.

1.  Download [**Windows Update Troubleshooter**](https://www.majorgeeks.com/files/details/windows_update_troubleshooter.html). Link download langsung dari situs pihak ketiga, yang diverifikasi dapat dipercaya dan sepenuhnya aman.

- https://www.majorgeeks.com/files/details/windows_update_troubleshooter.html

2.  Buka file **wu170509** yang baru saja didownload, dengan double klik file tersebut. Ini akan memulai identifikasi masalah dari update Windows.

{{< img src="/update-windows/1-2-windows-update-troubleshooter.png" caption="Install Windows Troubleshooter - 2" >}}

3.  Ikuti petunjuk. _**Windows Troubleshooter**_ dapat mengidentifikasi masalah apa pun, cukup klik untuk menerapkan perbaikan secara otomatis atau mendapatkan informasi lebih lanjut tentang masalah dengan pembaruan.

{{< img src="/update-windows/1-3-windows-update-troubleshooter.png" caption="Install Windows Troubleshooter - 3" >}}

{{< img src="/update-windows/1-4-windows-update-troubleshooter.png" caption="Install Windows Troubleshooter - 4" >}}

{{< img src="/update-windows/1-5-windows-update-troubleshooter.png" caption="Install Windows Troubleshooter - 5" >}}

{{< img src="/update-windows/1-6-windows-update-troubleshooter.png" caption="Install Windows Troubleshooter - 6" >}}

{{< img src="/update-windows/1-7-windows-update-troubleshooter.png" caption="Install Windows Troubleshooter - 7" >}}

{{< img src="/update-windows/1-8-windows-update-troubleshooter.png" caption="Install Windows Troubleshooter - 8" >}}


Perhatikan bahwa _Windows Update Troubleshooter_ bisa saja tidak bekerja. Melanjutkan dengan metode kami yang lain sampai Anda menemukan yang dapat bekerja untuk memperbaiki kesalahan gagal Pembaruan Windows.








### Metode 2: Pulihkan layanan terkait Pembaruan Windows

Jika layanan yang terkait dengan Pembaruan Windows mengalami masalah, telah dimatikan, atau ada pengaturan yang salah, mungkin itu penyebab kesalahan. Tetapi Anda dapat memperbaikinya dengan menjalankan beberapa perintah yang mengatur ulang layanan, yang berfungsi dengan mengirimkan pembaruan.

1. Tekan tombol **Windows** + **R** pada keyboard Anda untuk meluncurkan utilitas Run. Ketik "**cmd**" dan tekan **Ctrl** + **Shift** + **Enter**. Buka Command Prompt dengan izin administratif.

{{< img src="/update-windows/0-cmd-administrator.jpg" caption="Command Prompt dengan izin administratif" >}}

2. Jika diminta, pastikan untuk mengizinkan Command Prompt untuk membuat perubahan pada perangkat Windows. Yang berarti perlu masuk ke mode administrator.

3. Selanjutnya, Anda perlu menghentikan layanan yang terkait dengan mengunduh dan menginstal file Windows Update. Di dalam Command Prompt, masukkan baris berikut, tekan tombol Enter di antara setiap baris baru:

{{< code lang="PowerShell" >}}
net stop wuauserv
{{< /code >}}

{{< code lang="PowerShell" >}}
net stop cryptsvc
{{< /code >}}

{{< code lang="PowerShell" >}}
net stop bits
{{< /code >}}

{{< code lang="PowerShell" >}}
net stop appidsvc
{{< /code >}}

{{< img src="/update-windows/2-2-windows-update.jpg" caption="Update Windows 2-2" >}}


4. Setelah menghentikan layanan, masukkan dua perintah berikut, tekan tombol Enter setelah setiap baris:

{{< code lang="PowerShell" >}}
Ren %systemroot%\SoftwareDistribution SoftwareDistribution.old
{{< /code >}}

{{< code lang="PowerShell" >}}
Ren %systemroot%\system32\catroot2 catroot2.old
{{< /code >}}

{{< img src="/update-windows/2-3-windows-update.jpg" caption="Update Windows 2-3" >}}



5. Terakhir, restart layanan terkait Pembaruan Windows menggunakan perintah berikut. Sekali lagi, tekan Enter setelah setiap baris baru untuk menjalankan perintah:


{{< code lang="PowerShell" >}}
net start bits
{{< /code >}}

{{< code lang="PowerShell" >}}
net start wuauserv
{{< /code >}}

{{< code lang="PowerShell" >}}
net start appidsvc
{{< /code >}}

{{< code lang="PowerShell" >}}
net start cryptsvc
{{< /code >}}

{{< img src="/update-windows/2-4-windows-update.png" caption="Update Windows 2-4" >}}


6. Tutup Command Prompt dan periksa apakah Pembaruan Windows telah diperbaiki setelah menjalankan beberapa perintah tersebut.




### Metode 3: Jalankan pemindaian System File Checker (SFC)

Pemeriksa **File Sistem** adalah alat yang tersedia di Windows secara default. Metode ini juga bisa disebut "pemindaian SFC", dan ini adalah cara tercepat Anda untuk secara otomatis memperbaiki file sistem yang rusak dan masalah lainnya.

Beberapa pengguna telah berhasil dengan menjalankan pemindaian ini memperbaiki masalah dengan Update Windows gagal, macet, atau tidak dimulai.

1. Tekan tombol **Windows + R** (_bersamaan_) pada keyboard. Akan memunculkan utilitas Run.
2. Ketik "**cmd**" dan tekan tombol **Ctrl + Shift + Enter** pada keyboard. Pastikan _Command Prompt_ dengan izin administratif.
3. Jika diminta, klik **Ya** untuk mengizinkan Command Prompt melakukan perubahan pada perangkat Windows. Atau bisa ikuti cara berikut dengan ketik **CMD** pada kolom pencarian, lalu pilih **Run as Administratir**.

{{< img src="/update-windows/0-cmd-administrator.jpg" caption="Command Prompt dengan izin administratif" >}}

4. Setelah di Command Prompt, ketik perintah berikut dan tekan _Enter_ untuk menjalankannya: **sfc /scannow**

{{< img src="/update-windows/3-4-sfc-scannow.png" caption="System File Checker (SFC)" >}}

5. Tunggu pemindaian SFC untuk menyelesaikan pemindaian komputer Anda dan memperbaiki file yang rusak. Ini mungkin memakan waktu lama; pastikan tidak menutup Command Prompt atau mematikan komputer / laptop ketika sedang proses berjalan.
6. **Restart** perangkat setelah pemindaian selesai. Periksa apakah Anda dapat memperbarui Windows setelah restart selesai.





### Metode 4: Jalankan perintah DISM

DISM Tool memungkinkan Anda untuk mengidentifikasi dan memperbaiki masalah dengan sistem hanya dengan menjalankan beberapa baris perintah. Tool akan memeriksa kerusakan pada sistem dan secara otomatis menerapkan perbaikan untuk memulihkan file yang rusak atau hilang.

Anda dapat menggunakan alat ini untuk memperbaiki Update Windows untuk mendapatkan versi terbaru dari Windows 10 / 11.

1. Tekan tombol **Windows + R** (_bersamaan_) pada keyboard. Akan memunculkan utilitas Run.
2. Ketik "**cmd**" dan tekan tombol **Ctrl + Shift + Enter** pada keyboard. Pastikan _Command Prompt_ dengan izin administratif.
3. Jika diminta, klik **Ya** untuk mengizinkan Command Prompt melakukan perubahan pada perangkat Windows. Atau bisa ikuti cara berikut dengan ketik **CMD** pada kolom pencarian, lalu pilih **Run as Administratir**.

{{< img src="/update-windows/0-cmd-administrator.jpg" caption="Command Prompt dengan izin administratif" >}}

4. Setelah Command Prompt, Langkah selanjutnya memulai pemindaian DISM yang akan berjalan dan mencari masalah di seluruh sistem. Ketik perintah berikut dan tekan Enter untuk menjalankannya: 


{{< code lang="PowerShell" >}}
DISM.exe /Online /Cleanup-image /Scanhealth
{{< /code >}}

{{< img src="/update-windows/4-2-dism-restorehealth.png" caption="Scanhealth" >}}


5. Selanjutnya, Anda perlu menjalankan perintah sekali lagi, untuk memperbaiki masalah yang ditemukan di sistem Windows Anda. Cukup ketik baris berikut dan tekan Enter lagi:

{{< code lang="PowerShell" >}}
DISM.exe /Online /Cleanup-image /Restorehealth
{{< /code >}}

{{< img src="/update-windows/4-3-dism-restorehealth.png" caption="Restorehealth" >}}


6.  Tunggu hingga proses selesai. Setelah selesai, tutup jendela Command Prompt dan mulai ulang perangkat. Periksa apakah kesalahan Update Windows masih muncul?





### Metode 5: Nonaktifkan sementara Antivirus

Aplikasi antivirus pihak ketiga diketahui menyebabkan masalah dengan jaringan dan koneksi internet Windows. Yang berarti dapat mengganggu proses download saat mencoba memperbarui sistem.

Anda dapat dengan mudah menguji apakah perangkat lunak antivirus mengganggu koneksi dengan menonaktifkannya untuk sementara.

{{< panel style="info" >}}
**Catatan** : Pastikan Anda [mengaktifkan **Windows Defender**](https://www.youtube.com/watch?v=_UCUSC6Fi1Q) saat mengoperasikan sistem Windows, tanpa antivirus pihak ketiga. _Windows Defender_ adalah solusi keamanan terintegrasi Windows yang tidak menyebabkan masalah dan memberikan perlindungan dasar terhadap sebagian besar ancaman.
{{< /panel >}}

{{< img src="/update-windows/0-windows-defender.png" caption="Windows Defender" >}}




1. Input pada kolom pencarian dengan kata kunci **Task Manager**.

{{< img src="/update-windows/5-1-task-manager.png" caption="Task Manager" >}}

2. Jika Task Manager ditampilkan dalam mode ringkas, pastikan untuk memperluas detail dengan mengklik tombol "**More Details**".

{{< img src="/update-windows/5-2-task-manager.png" caption="More Details" >}}

3. Beralih ke tab **Start-up** menggunakan menu header yang terletak di bagian atas jendela.
4. Temukan aplikasi antivirus dari daftar dan pilih dengan mengkliknya sekali.
5. Klik tombol **End Task** yang sekarang terlihat di kanan bawah jendela. Dengan metode ini akan menonaktifkan aplikasi dari _sistem latar_ ketika menggunakan perangkat, sebagai contoh dengan antivitus dari **Avast**, sesuaikan dengan antivirus yang Anda gunakan.

{{< img src="/update-windows/5-5-task-manager.png" caption="Anti Virus" >}}

6. **Restart**  komputer / laptop dan lihat apakah Pembaruan Windows berfungsi setelah menonaktifkan antivirus pihak ketiga. Jika ya, Anda mungkin perlu menyesuaikan software, yang dapat mengganggu Update Windows di masa mendatang.






### Metode 6: Pulihkan Windows 10 dari cadangan

Jika beberapa metode masih gagal, kami sarankan untuk memeriksa Restore Point di sistem Windows Anda.Gunakan ini untuk memulihkan komputer ke keadaan ketika Update Windows dapat download sumber dan menginstal dengan benar, lalu perbarui ke versi terbaru.

1. Cari bilah pencarian lalu input kata "*restore*".
2. Lalu buka "**Create a restore point**" setelah itu akan diarahkan ke jendela System Properties.
3.  Di tab "Perlindungan Sistem" / "**System Protection**", klik pada menu " **System Restore**". Selanjutnya akan membuka jendela dialog baru lainnya, apabila __System Restore__ tidak dapat klik abaikan **metode 6**.
4.  Ikuti petunjuk di layar untuk menemukan Restore Point sebelumnya yang tersimpan di perangkat Windows. Cukup memulihkannya (_restore_) dan mencoba memperbarui sistem sekali lagi.

Kami berharap panduan ini dapat membantu Anda memecahkan masalah kesalahan "**Pembaruan Windows terus gagal**" pada sistem Windows 10 khususnya.





### Metode 7. Pause Updates

Beberapa kendala tidak dapat Update Windows karena pembaruan terjeda, bagaimana cara aktifkan?. Buka **Pengaturan> Update & Security > Update Windows** dan pilih Opsi Lanjutan / **Advanced Options**. Dengan asumsi Anda menggunakan versi Windows 10 yang relatif baru, seperti screenshot layar berikut:

{{< img src="/update-windows/6-1-pause-updates.jpg" caption="Pause Updates" >}}


Nonaktifkan **Pause Updates**. Mulai ulang / Restart laptop. Kemudian, setelah perangkat booting sepenuhnya, kembali ke menu tadi lalu pilih Pause Updates dalam keadaan mati.

Jika memberi tahu Windows untuk menjeda pembaruan, Anda akan menghapus semua pembaruan yang sudah didownload. Silakan dan coba Pembaruan Windows lagi. Semoga berhasil. Ini jauh lebih mudah (dan tidak terlalu membuat stres) daripada menggunakan metode diatas untuk dapat update Windows.

