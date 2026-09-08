# manajemen-pasokan-kafe

Nama         : Muhammad Akbar Din Islami (2495114049), Dimas Ferdiansyah (2495114036)
Kelas        : Karyawan (K)
Mata Kuliah  : Pemograman Web Lanjut


Website  : Sistem Informasi Manajemen Pasokan Bahan Kafe (SIPAS-KAFE)
Aktor dan Peran :
1. Supplier
   Peran : Pihak yang mengirim bahan dari luar ke gudang, datanya dicatat dalam laporan pengiriman
   Akses Sistem : Tidak memiliki akses ke aplikasi, hanya sebagai data referensi yang dicatat Admin Gudang
2. Admin Gudang
   Peran : Mengelola stok di gudang, memproses permintaan pasokan, membuat laporan pengiriman, mengelola data supplier, serta menangani masalah akun pengguna (lupa sandi, dll.)
   Akses Sistem : Akses penuh modul gudang & pengelolaan data dasar
3. Staff Kafe
   Peran : Mengajukan permintaan bahan, memverifikasi barang yang diterima, mencatat stok masuk ke kafe
   Akses Sistem : Akses modul permintaan & penerimaan
4. Manager
   Peran : Melihat laporan pasokan, memantau riwayat permintaan & pengiriman, mengawasi ketersediaan stok
   Akses Sistem : Akses laporan & pemantauan saja

Kebutuhan Fungsional
F-01. Sistem dapat menyimpan dan mengelola data pemasok (nama, alamat, kontak) yang dikelola oleh Admin Gudang
F-02. Sistem dapat memproses pengajuan permintaan pasokan bahan dari kafe ke gudang, mencatat jenis bahan, jumlah, satuan, dan tanggal kebutuhan
F-03. Sistem dapat menampilkan daftar permintaan masuk kepada Admin Gudang beserta statusnya (Menunggu Diproses / Sedang Dikirim / Selesai)
F-04. Admin Gudang dapat mencatat laporan pengiriman bahan dari pemasok ke gudang, mencantumkan nama pemasok, daftar barang, jumlah, dan tanggal kirim
F-05. Admin Gudang dapat membuat laporan pengiriman ke kafe berdasarkan permintaan yang disetujui, mencatat tanggal kirim dan nomor pengiriman
F-06. Staf Kafe dapat mencatat penerimaan barang, membandingkan jumlah dikirim vs diterima, lalu mengubah status permintaan menjadi selesai
F-07 Admin Gudang dapat mengelola akun pengguna termasuk mereset sandi jika pengguna lupa sandi
F-08 Sistem dapat menampilkan laporan riwayat pasokan dalam periode tertentu, berisi data permintaan, pengiriman, penerimaan, dan informasi pemasok

Kebutuhan Nonfungsional dan Ukuran/Indikator
1. Kinerja : Halaman daftar data dapat dimuat dalam waktu ≤ 3 detik pada koneksi internet standar
2. Keamanan : Hanya pengguna terdaftar yang dapat mengakses aplikasi; setiap perubahan data tercatat siapa dan kapan melakukannya, Supplier tidak memiliki akun dan tidak dapat login.
3. Keandalan dan Pemulihan : Sistem tersedia minimal 98% dalam satu bulan; permintaan reset sandi dapat diproses dan dikembalikan maksimal dalam 1x24 jam kerja

4. Batasan Sistem

1. Sistem hanya mengelola alur pasokan dari gudang ke kafe serta pencatatan pengiriman bahan dari pemasok ke gudang. Supplier tidak memiliki akses login maupun hak pengelolaan data ke dalam aplikasi.

2. Pengelolaan akun pengguna, termasuk penanganan lupa sandi, dilakukan secara manual oleh Staf Gudang melalui pengaturan sistem; tidak ada fitur pemulihan sandi mandiri oleh pengguna.

3. Perhitungan stok dilakukan saat pencatatan pengiriman dan penerimaan; sistem tidak terhubung otomatis dengan alat pemindai atau perangkat keras gudang.

5. User Story dengan Acceptance Criteria

US-01: Mencatat Data Pemasok & Pengiriman Barang dari Pemasok

Sebagai Staf Gudang, Saya ingin mencatat data pemasok dan pririman bahan yang masuk dari pemasok, Agar sumber bahan dapat terlacak meskipun pemasok tidak mengakses sistem.
Kriteria Penerimaan:

Staf Gudang dapat menambah, mengubah, dan menghapus data pemasok (nama, alamat, kontak).

Saat mencatat pengiriman bahan masuk, formulir menyertakan pilihan nama pemasok, daftar barang, jumlah, satuan, dan tanggal pengiriman.

Data pemasok hanya muncul sebagai pilihan dalam formulir pencatatan; tidak ada halaman login atau akses khusus untuk pemasok.

US-02: Mengajukan & Memproses Permintaan Pasokan Bahan

Sebagai Staf Kafe, Saya ingin mengajukan permintaan bahan ke gudang, Agar kebutuhan stok di kafe dapat terpenuhi tepat waktu.

Kriteria Penerimaan:

Formulir permintaan dapat diisi dengan nama bahan, jumlah yan Jutuhkan, satuan, dan tanggal kebutuhan.

Sistem menolak simpan jika ada kolom wajib yang kosong

US-03: Mengelola Akun & Membantu Pengguna Lupa Sandi

Sebagai Staf Gudang, Saya ingin dapat mereset sandi pengguna yang lupa, Agar pengguna dapat kembali menggunakan aplikasi.

Kriteria Penerimaan:

Staf Gudang dapat melihat daftar akun pengguna dan mengubah sandi baru secara manual.

Sistem mencatat siapa dan kapan melakukan perubahan sandi pada riwayat aktivitas.

Pengguna tidak dapat mengakses fitur ini hanya Staf Gudang yang memiliki hak akses pengelolaan akun.

1. Use Case Naratif - Fitur Utama

Nama Use Case: Pencatatan Pengiriman dari Pemasok & Alur Pasokan dari Gudang ke Kafe

Aktor Utama: Staf Gudang, Staf Kafe

Aktor Pendukung: Pemasok (tidak memiliki akses aplikasi)

Ringkasan: Staf Gudang mencatat pengiriman bahan yang dikirim pemasok ke gudang; kemudian Staf Kafe mengajukan permintaan bahan ke gudang; Staf Gudang memproses, menyiapkan barang, lalu mengirim ke kafe; Staf Kafe menerima barang dan mengonfirmasi. Pengelolaan akun termasuk penanganan lupa sandi dilakukan oleh Staf Gudang.

Alur Normal:

1. Pemasok mengirim bahan ke gudang → Staf Gudang menerima barang dan mencatat pengiriman di sistem, memilih nama pemasok serta memasukkan rincian barang dan jumlah.

2. Staf Kafe memeriksa stok di kafe dan mengisi formulir perminta sokan ke gudang.

3. Sistem menyimpan permintaan dengan status "Menunggu Diproses".

4. Staf Gudang membuka daftar permintaan, menyiapkan barang sesuai permintaan, lalu membuat laporan pengiriman.

5. Sistem mengubah status menjadi "Sedang Dikirim".

6. Barang dikirim ke kafe → Staf Kafe memeriksa kesesuaian barang mencatat penerimaan sistem mengubah status menjadi "Selesai".

7. Jika ada pengguna yang lupa sandi menghubungi Staf Gudang → Staf Gudang mereset sandi lewat sistem dan memberitahukan sandi baru kepada pengguna.
