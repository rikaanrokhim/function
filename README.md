# Function PHP
Dalam merancang kode program, kadang kita sering membuat kode yang melakukan tugas yang sama secara berulang-ulang, seperti membaca tabel dari database, menampilkan penjumlahan, dan lain-lain.
Tugas yang sama ini akan lebih efektif jika dipisahkan dari program utama, dan dirancang menjadi sebuah fungsi.
Fungi dari _function_ sendiri adalah mempersingkat sebuah aksi yang ingi dilakukan didalam sebuah penulisan kode program.


## Fungsi Built-in

Adalah fungsi yang secara default telah disediakan oleh PHP. Dikelompokkan sebagai berikut :
* Fungsi Array
* Fungsi Class/Object
* Fungsi Database
* Fungsi Pengolah PDF
* Fungsi Pengolah File
* Fungsi Pengolah Gambar
* Fungsi Matematika
* Fungsi String
* Fungsi Tanggal dan Waktu
* Fungsi Reguler Ekspresi
* Fungsi Variabel


## Menulis Fungsi PHP

* Sintag
```php
<?php
    //definisi fungsi
    function writeMsg()
    {
        echo "Selamat datang!";
    }
    //memanggil fungsi
    writeMsg();
```

## Fungsi PHP dengan Parameter

* Sintag
```php
<?php
    function addFunction($no1, $no2)
    {
        $jumlah = $no1 + $no2;
        echo "Jumlah : $jumlah";
    }
    addFunction(10, 20);
```

## Argumen Fungsi

Argumen fungsi ditulis dalam tanda kurung dan dapat berupa tipe data apapun baik string, array, object, boelan, dsb.., selain itu argumen juga dapat dikosongkan, 
contoh:

* Sintag
``php
<?php
    // Tanpa argumen
    function nama_bulan() 
    {
        echo 'Agustus';
    }
    nama_bulan(); // Hasil Agustus
```

Contoh berikutnya definisikan argumen, sehingga  dapat mencetak nama bulan sesuai dengan yang dinginkan:

```php
<?php
    function nama_bulan($bulan) 
    {
        echo $bulan;
    }
    nama_bulan('Januari'); // Hasil Januari

Lebih lanjut, argumen dari fungsi ini dapat didefinisikan lebih dari satu, caranya, pisahkan argumen dengan tanda koma, contoh:

```php
<?php
    function nama_bulan($bulan, $tahun) 
    {
        echo $bulan . ' ' . $tahun;
    }
    nama_bulan('Januari', 2016); // Hasil Januari 2016
```

## Nilai Default Argumen

Kita dapat mendefinisikan nilai default dari argumen, sehingga memudahkan pemanggilan fungsi karena tidak perlu menulis argumen terlalu banyak, contoh:

```php
<?php
    function nama_bulan($bulan, $tahun = 2016) 
    {
        echo $bulan . ' ' . $tahun;
    }
    nama_bulan('Januari'); // Hasil Januari 2016
Nilai default argumen ini bisa kita isi tipe data apa saja seperti boelan (true, false), null, array, object, dll

## Nilai Kembalian – Return Value

* Menggunakan return

Nilai kembalian ini maksudnya fungsi yang kita panggil tadi akan menghasilkan nilai tertentu, nilai tersebut bisa bertipe apa jasa seperti: boelan, float, array, object, dll
Nilai kembalian ini dijalankan dengan menggunakan keyword `return`, contoh:

```php
<?php
    function nama_bulan($bulan) 
    {
        $nama_bulan = array (1 => 'Januari', 2 => 'Februari', 3 => 'Maret');
        return $nama_bulan[$bulan];
    }
    // date('n') akan menghasilkan bulan sekarang dalam bentuk 1 digit, misal 3 untuk Januari
    $bulan = nama_bulan(date('n')); // Hasil Maret 
        echo $bulan . ' ' . date('Y'); // Hasil Maret 2016
```

* Return value lebih dari satu nilai

``php
<?php
?php
    function nama_bulan($bulan) 
    {
        $nama_bulan = array (1 => 'Januari', 2 => 'Februari', 3 => 'Maret');
        $semester   = $bulan < 7 ? 1 : 2;
        return array('bulan' => $nama_bulan[$bulan],
                    'semester' => $semester
                );
    }
    $bulan = nama_bulan(3);
        echo '<pre>'; print_r($bulan);
```

* Anonymous Function

Anonymous function atau disebut juga closure dapat diartikan fungsi tanpa nama (anonymous). 
Fungsi ini umumnya digunakan pada fungsi-fungsi yang membutuhkan callback (fungsi yang dipanggil oleh fungsi lainnya).
Fungsi yang membutuhkan callback ini bisa built-in function seperti preg_replcace_callback, array_map, array_walk, dll maupun user-defined function.

```php
<?php
$kendaraan  = array('Mobil', 'Motor', 'Sepeda');
$upper      = array_map('toupper', $kendaraan);
function toupper($array_val) 
{
    return strtoupper($array_val);
}
    echo '<pre>'; print_r($upper);
```

## Fungsi String

Daftar Fungsi yang Sering digunakan :

Nama Fungsi | Keterangan
----------- | ----------
`Strlen()` | Digunakan untuk mengetahui jumlah karakter dalam suatu string (teks)
`Strstr()` | Mengambil suatu string mulai posisi setelah suatu substring, case sensitive
`Stristr()` | Strstr, tidak case sensitive
`Strchr()` | Sama dengan strstr()
`Substr()` | Digunakan untuk mengambil sebagian string
`Trim()` | Menghilangkan spasi sebelum huruf pertama string dan sesudah huruf terakhir string
`Ltrim()` | Menghilangkan spasi sebelum huruf pertama string (kiri)
`Rtrim()` | Menghilangkan spasi sesudah huruf  terakhir string (kanan)
`Strtolower()`| Seluruh string menjadi huruf kecil
`Strtoupper()` | Seluruh string menjadi huruf kapital
`Ucfirst()` | Awal string menjadi huruf kapital
`Strrev()` | Membalik urutan string
`Str_replace()` | Menganti sebagian string yang dicari dengan string lain
`Strcmp()` | Membandingkan biner dua string, case sensitive

## Link Belajar

* [PHP 5 Function](https://www.w3schools.com/php/php_functions.asp)
* [PHP FUnction](https://www.tutorialspoint.com/php/php_functions.htm)
* [Memahami Fungsi Pada PHP dan Cara Membuatnya](http://jagowebdev.com/memahami-dan-membuat-fungsi-pada-php/)