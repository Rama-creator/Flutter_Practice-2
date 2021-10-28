# Beberapa hal yang belum dijelaskan pada bagian pertama

# Add Icons to the List 
Pada langkah ini, akan ditambahkan ikon hati ke setiap baris. Pada langkah berikutnya, akan membuatnya dapat diketuk dan menyimpan favorit.
1. dd a _saved Setel ke _RandomWordsState. Set ini menyimpan pasangan kata yang disukai pengguna. Set lebih disukai daripada Daftar karena Set yang diterapkan dengan benar tidak mengizinkan entri duplikat.
2. Dalam fungsi _buildRow, tambahkan tanda centang yang sudah Disimpan untuk memastikan bahwa pasangan kata belum ditambahkan ke favorit.
  Di _buildRow() , Anda juga akan menambahkan ikon berbentuk hati ke objek ListTile untuk mengaktifkan favorit. Pada langkah berikutnya, Anda akan menambahkan kemampuan untuk berinteraksi dengan ikon hati.
3. Tambahkan ikon setelah teks.
4. Panaskan ulang aplikasi.

Probblem / Masalah
Jika aplikasi Anda tidak berjalan dengan benar, Anda dapat menggunakan kode di tautan berikut untuk kembali ke jalur semula.
lib/main.dart

# Add interactivity
Pada langkah ini, akan membuat ikon hati dapat diketuk. Saat pengguna mengetuk entri dalam daftar, mengubah status favoritnya, pasangan kata itu ditambahkan atau dihapus dari kumpulan favorit yang disimpan.
Untuk melakukannya, Anda akan memodifikasi fungsi _buildRow. Jika entri kata telah ditambahkan ke favorit, mengetuknya lagi akan menghapusnya dari favorit. Saat sebuah petak diketuk, fungsi memanggil setState() untuk memberi tahu kerangka kerja bahwa status telah berubah.
1. Tambahkan onTap ke metode _buildRow (Tips: Dalam framework gaya reaktif Flutter, memanggil setState() memicu panggilan ke metode build() untuk objek State, yang menghasilkan update ke UI)
2. Panaskan ulang aplikasi.
   kita harus dapat mengetuk ubin apa saja untuk memfavoritkan atau membatalkan favorit entri. Mengetuk ubin menghasilkan animasi percikan tinta implisit yang berasal dari titik ketuk.
   
# Navigate to a new screen 
Pada langkah ini, akan menambahkan halaman baru (disebut rute di Flutter) yang menampilkan favorit. Anda akan belajar cara menavigasi antara rute asal dan rute baru.
Di Flutter, Navigator mengelola tumpukan yang berisi rute aplikasi. Mendorong rute ke tumpukan Navigator memperbarui tampilan ke rute itu. Memunculkan rute dari tumpukan Navigator akan mengembalikan tampilan ke rute sebelumnya.
Selanjutnya, akan menambahkan ikon daftar ke AppBar dalam metode build untuk _RandomWordsState. Ketika pengguna mengklik ikon daftar, rute baru yang berisi favorit yang disimpan didorong ke Navigator, menampilkan ikon.
1. Tambahkan ikon dan tindakan yang sesuai ke metode build.
2. Tambahkan fungsi _pushSaved() ke kelas _RandomWordsState.
3. Panaskan ulang aplikasi. Ikon daftar a114478ae13b853.png muncul di bilah aplikasi. Mengetuknya belum menghasilkan apa-apa karena fungsi _pushSaved kosong.
  Selanjutnya, akan membuat rute dan mendorongnya ke tumpukan Navigator. Tindakan itu mengubah layar untuk menampilkan rute baru. Konten untuk halaman baru dibangun di properti pembuat MaterialPageRoute dalam fungsi anonim.
4. Panggil Navigator.push, seperti yang ditunjukkan di bawah ini, yang mendorong rute ke tumpukan Navigator. IDE akan mengeluh tentang kode yang tidak valid, tetapi akan memperbaikinya di bagian selanjutnya.
Selanjutnya, menambahkan MaterialPageRoute dan pembuatnya. Untuk saat ini, tambahkan kode yang menghasilkan baris ListTile. Metode divideTiles() dari ListTile menambahkan jarak horizontal antara setiap ListTile. Variabel yang dibagi menampung baris terakhir yang dikonversi ke daftar oleh fungsi kenyamanan, toList().
5. Panaskan ulang aplikasi. Favoritkan beberapa pilihan dan ketuk ikon daftar di bilah aplikasi. Rute baru muncul berisi favorit. Perhatikan bahwa Navigator menambahkan tombol "Kembali" ke bilah aplikasi. Anda tidak harus mengimplementasikan Navigator.pop secara eksplisit. Ketuk tombol kembali untuk kembali ke rute asal.

# change the UI using themes 
Pada langkah ini, memodifikasi tema aplikasi. Tema mengontrol tampilan dan nuansa aplikasi. dapat menggunakan tema default, yang bergantung pada perangkat fisik atau emulator, atau menyesuaikan tema untuk mencerminkan merek.
dapat juga dengan mudah mengubah tema aplikasi dengan mengonfigurasi kelas ThemeData. Aplikasi menggunakan tema default, akan tetapi mengubah warna utama aplikasi menjadi putih.
1. Ubah warna di kelas MyApp
2. Panaskan ulang aplikasi. Seluruh latar belakang sekarang berwarna putih, bahkan bilah aplikasi.
Sebagai latihan, gunakan ThemeData untuk mengubah aspek lain dari UI. Kelas Warna di pustaka Material menyediakan banyak konstanta warna yang bisa Anda mainkan. Hot reload membuat eksperimen dengan UI cepat dan mudah.
