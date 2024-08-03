# Penggunaan Tag `<b:class>` di Blogger

Tag `<b:class>` adalah tag instruksi di XML yang digunakan untuk menambahkan nilai ke atribut `class` pada elemen induknya dalam Blogger. Tag ini sangat berguna dalam pengembangan tema dan tata letak pada platform Blogger.

## Sintaks Dasar
```
<div>
  <b:class cond='CONDITION' name='CLASS_NAME' />
</div>
```
Tag ini bekerja di seluruh kode XML kecuali di dalam markup `<![CDATA[`. Beberapa tag `<b:class>` dapat digunakan secara bersamaan, tetapi tidak boleh bersarang.

## Atribut Tag
+ `name` : Nama kelas yang akan ditambahkan ke elemen induk. Bisa berupa string atau ekspresi Blogger yang menghasilkan string (wajib), untuk `expr:` Diizinkan.
+ `cond` : Kondisi boolean yang menentukan apakah atribut akan ditambahkan dalam kondisi tertentu (opsional).

## Contoh Penggunaan

### Menambahkan Class Sederhana
```
<div>
  <b:class name='footer' />
</div>
```
Hasil: `<div class='footer'></div>`

### Menambahkan Class dengan Kondisi
```
<div>
  <b:class cond='data:view.isHomepage' name='footer' />
</div>
```
Hasil jika kondisi benar: `<div class='footer'></div>`
Hasil jika kondisi salah: `<div></div>`

### Menambahkan Class ke Class yang Sudah Ada
```
<div class='section'>
  <b:class name='footer' />
</div>
```
Hasil: `<div class='section footer'></div>`

### Menggabungkan Beberapa Class
```
<div class='section'>
  <b:class name='footer' />
  <b:class name='left' />
</div>
```
Hasil: `<div class='section footer left'></div>`

### Menambahkan Class Variabel
```
<div>
  <b:class expr:name='data:view.isHomepage ? "superfooter" : "footer"' />
</div>
```
Hasil jika halaman utama: `<div class='superfooter'></div>`
Hasil jika halaman lain: `<div class='footer'></div>`

### 
