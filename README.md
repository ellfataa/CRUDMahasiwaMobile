TUGAS 8 - PERTEMUAN 9 (Praktikum Pemrograman Mobile)
====================================================

Nama        : Luthfi Emillulfata

NIM         : H1D022017

Shift Lama  : D

Shift Baru  : C

=====================================================

Penjelasan PROSES CRUD

1. Pertama-tama kita membuat Database API nya terlebih dahulu, disini saya membuat database dengan nama db_mhs. Lalu didalamnya terdapat sebuah tabel mahasiswa yang digunakan untuk proses CRUD nya.

   ![image](https://github.com/user-attachments/assets/94648058-20bc-4a53-b78e-a5cf2c2bbf22)

2. Setelah membuat database, langkah selanjutnya yaitu membuat folder untuk backend agar kode-kodenya nanti dapat terhubung dengan database API nya. Folder tersebut kita buat di dalam direktori www karena saya menggunakan tools Laragon.

3. Di dalam folder tadi kita buat beberapa file .php nya, antara lain koneksi.php, tampil.php, tambah.php, lihat.php, hapus.php, edit.php

   a) File koneksi.php

      ![image](https://github.com/user-attachments/assets/377744ee-5459-4b25-8756-e18afdc66d5f)

      File koneksi.php tersebut digunakan untuk melakukan koneksi dengan database API.

   b) File tampil.php

      ![image](https://github.com/user-attachments/assets/c69c0ec0-e3f2-4ee7-8d1b-0e8aa15be091)

      File tampil.php ini berfungsi untuk menampilkan data mahasiswa secara keseluruhan.
      
   c) File tambah.php

      ![image](https://github.com/user-attachments/assets/e64b7be0-02d2-4113-a1ca-af6b66b16118)

      File tambah.php digunakan untuk menambahkan data mahasiswa dengan insert nama dan jurusan.

   d) File lihat.php

      ![image](https://github.com/user-attachments/assets/0236b369-365d-4924-a720-f8cd27d28c8d)

      File lihat.php ini berfungsi untuk mengambil satu data berdasarkan id data mahasiswa.

   e) File hapus.php

      ![image](https://github.com/user-attachments/assets/1a892fca-7b65-4063-95fa-d44f1b74357c)

      File hapus.php ini berfungsi untuk menghapus data mahasiswa berdasarkan id data mahasiswa tersebut.

   f) File edit.php

      ![image](https://github.com/user-attachments/assets/88690897-a4e0-4202-a174-932aeb7c53a3)

      File edit.php digunakan untuk mengedit data mahasiswa yang tadinya sudah ditambah terlebih dahulu.
  
4. Setelah membuat file-file .php nya, lalu kita membuat projek ionicnya seperti biasa dengan memasukkan perintah ionic star 'nama_projek', lalu pilih framework Angular dan pilih template blank

5. Selanjutnya ketika projek ionic nya sudah berhasil dibuat lalu kita membuat halaman mahasiswa dengan memasukkan perintah "ionic g pg mahasiswa", serta membuat service API dengan perintah "ionic g s service/api" 

6. Setelah itu deklarasikan provideHttpClient pada app/app.module.ts dengan tujuan agar aplikasi dapat berinteraksi dengan API.

   ![image](https://github.com/user-attachments/assets/7f79b1dc-1e46-427d-87cd-f5e669f03ac7)

7. Lalu kita edit file api.service.ts pada service/api yang sudah kita buat sebelumnya. Disini kita mengedit apiURL nya menjadi 'http://localhost/mahasiswa'.

   ![image](https://github.com/user-attachments/assets/c2e3269b-3092-4f83-a68a-8312d62d29ac)

8. Setelah itu kita edit pada halaman mahasiswanya, yaitu di file mahasiswa.page.html dan mahasiswa.page.ts

   **a) File mahasiswa.page.html**

      Kode dibawah ini menampilkan header bertuliskan "Data Mahasiswa" dengan efek transparan, serta tombol "Tambah Mahasiswa" yang memanggil fungsi `openModalTambah()` saat diklik untuk menambahkan data mahasiswa.

      ![image](https://github.com/user-attachments/assets/0da15cce-e3b8-455c-b7ce-d17dde06d7d4)

      Kode dibawah mendefinisikan modal "Tambah Mahasiswa" yang muncul saat `modalTambah` diaktifkan. Modal ini memiliki tombol "Batal" untuk menutup modal dan form input untuk mengisi nama dan jurusan mahasiswa, yang terikat pada variabel `nama` dan `jurusan`. Setelah data diisi, tombol "Tambah Mahasiswa" memanggil fungsi `tambahMahasiswa()` untuk menambahkan data mahasiswa.

      ![image](https://github.com/user-attachments/assets/a0357f6b-7162-4683-9f35-969288dc9d8d)

      Kode dibawah membuat modal "Edit Mahasiswa" yang ditampilkan saat `modalEdit` aktif. Modal ini memiliki tombol "Batal" untuk menutup modal dan dua input untuk mengedit nama dan jurusan mahasiswa, yang terhubung ke variabel `nama` dan `jurusan`. Tombol "Simpan Perubahan" akan memanggil fungsi `editMahasiswa()` untuk menyimpan perubahan data mahasiswa.

      ![image](https://github.com/user-attachments/assets/a91df6de-8d08-4a66-b1a7-1cddc750ae31)

      Kode dibawah menampilkan daftar mahasiswa menggunakan `<ion-card>` yang berulang untuk setiap item di `dataMahasiswa`. Setiap kartu menampilkan nama dan jurusan mahasiswa, serta dua tombol: "Edit" untuk membuka modal edit dengan `openModalEdit()` dan "Hapus" untuk menghapus data mahasiswa menggunakan fungsi `hapusMahasiswa()`.

      ![image](https://github.com/user-attachments/assets/7e742f96-221e-4dcd-a0b7-15a0f6178c7d)

   ========================================================================================================

   **b) File mahasiswa.page.ts**

        ![image](https://github.com/user-attachments/assets/f3af76eb-146c-4e2a-a57d-6cd8c82c61cc)

        ![image](https://github.com/user-attachments/assets/38c49399-f938-4dd3-b5c8-e6e6aa8787a7)

        ![image](https://github.com/user-attachments/assets/e4a44580-f5c1-4212-b7c4-39aa42941308)

        Kode diatas merupakan komponen Angular untuk halaman "Mahasiswa" dalam aplikasi Ionic yang mengelola data mahasiswa melalui berbagai interaksi. Komponen ini menggunakan `ModalController` dan `AlertController` dari Ionic untuk menampilkan modal (popup) dan alert konfirmasi. Data mahasiswa disimpan dalam array `dataMahasiswa`, dan komponen ini menyediakan fitur untuk menambah, mengedit, dan menghapus data mahasiswa melalui API dengan memanfaatkan `ApiService`. Variabel seperti `id`, `nama`, dan `jurusan` digunakan untuk menyimpan data mahasiswa yang sedang dipilih atau diubah.

        Pada saat halaman dimuat, fungsi `ngOnInit()` akan memanggil metode `getMahasiswa()` untuk mengambil data mahasiswa dari server dan menampilkannya di halaman. Fungsi `tambahMahasiswa()` digunakan untuk menambahkan mahasiswa baru ke dalam daftar jika input nama dan jurusan telah diisi, sedangkan `editMahasiswa()` digunakan untuk mengedit data mahasiswa yang sudah ada. Kedua proses ini berinteraksi dengan API untuk menyimpan perubahan data, dan setelah berhasil, halaman akan diperbarui secara otomatis.

        Fungsi lainnya, seperti `hapusMahasiswa()`, akan menampilkan konfirmasi melalui alert sebelum menghapus data mahasiswa dari server. Modal untuk menambah atau mengedit data mahasiswa dibuka dengan memanggil fungsi `openModalTambah()` atau `openModalEdit()`, yang memungkinkan pengguna untuk melakukan perubahan pada data. Setelah modal ditutup, input form akan direset menggunakan fungsi `resetModal()`, yang memastikan tidak ada data lama yang tertinggal di form.

=======================================================

SCREENSHOT TAMPILAN
===================

1. Tampilan Data Mahasiswa

   ![image](https://github.com/user-attachments/assets/1b9ef213-cd6c-49f9-b7dc-18427d4da28c)

2. Tambah Mahasiswa

   ![image](https://github.com/user-attachments/assets/73cd0ad0-6499-4c81-877c-022a2d6ce234)

   ![image](https://github.com/user-attachments/assets/52f55fca-9334-4539-845a-9badd4a47fd3)

   **Data berhasil ditambah**

   ![image](https://github.com/user-attachments/assets/3b8e5c2d-e0ed-4f11-9ed5-6da570e64c9b)

3. Edit Mahasiswa

   **Sebelum diedit**

   ![image](https://github.com/user-attachments/assets/a6a46d83-cf27-4b99-94ac-2a351f5657e0)

   **Setelah diedit**

   ![image](https://github.com/user-attachments/assets/b116ae62-ea09-4ad5-9fcf-57705f21b1a8)
   ![image](https://github.com/user-attachments/assets/34eec969-84bc-4f65-a8b6-9d6365b1eb00)

5. Hapus Mahasiswa

   **Sebelum dihapus untuk data Gojo**

   ![image](https://github.com/user-attachments/assets/5ce9b0e9-73ec-4c19-8a3a-4032b4cbb3e7)

   **Alert Konfirmasi Hapus (YA / TIDAK)**

   ![image](https://github.com/user-attachments/assets/2e3aadca-a1a6-4e46-ba5e-4279da681cf1)

   **Setelah dihapus untuk data Gojo**

   ![image](https://github.com/user-attachments/assets/c159e5af-811a-43de-97e5-b8525fc24668)
