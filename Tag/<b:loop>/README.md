# Panduan Penggunaan Tag `<b:loop>` dalam Blogger

## Deskripsi
Tag `<b:loop>` dalam Blogger digunakan untuk mengakses item-item dalam array (tabel). Tag ini bekerja di seluruh kode XML kecuali di dalam tag `<![CDATA[...]]>`.

## Sintaks
```xml
<b:loop values='ARRAY' var='VARIABLE_NAME'>
  <!-- Blok kode yang akan dieksekusi -->
</b:loop>
```
## Atribut
+ `values` : Array yang akan diakses. Bisa berupa nilai eksplisit, data, atau ekspresi Blogger dengan tipe array (wajib).
+ `var` : Nama variabel yang akan menyimpan nilai item dari array (wajib).
+ `index` : Nama indeks untuk mendapatkan nomor indeks dalam loop. Nilai yang diharapkan adalah string (opsional).
+ `reverse` : Mengubah arah loop. Nilai yang diharapkan adalah boolean (true atau false) (opsional).

## Contoh
```xml
<b:loop values='data:posts' var='post'>
  <!-- ITEM -->
  <data:post.title/>
</b:loop>
```
