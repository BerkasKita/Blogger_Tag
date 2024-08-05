# Penjelasan Tag <b:widget> dalam Blogger
## Deskripsi
Tag `<b:widget>` dalam Blogger adalah elemen layout yang hanya dapat ditempatkan di dalam tag `<b:section>`. Tag ini berisi kode XML dari gadget yang digunakan dalam halaman Blogger.
## Sintaks
```xml
<b:widget cond='true' id='ID_NAME' locked='false|true' title='Title_Widget' type='Type'>...</b:widget>
```
Setiap `<b:widget>` harus berada di dalam tag `<b:section>` dan tidak dapat mengandung tag `<b:widget>` lain. Tag <b:widget> hanya dapat mengandung tag `<b:includable>`, di mana satu di antaranya wajib memiliki identifier `main`.

## Atribut
Beberapa atribut dapat ditambahkan pada tag ini, baik yang wajib maupun opsional
+ `id` : Identifikasi gadget, terdiri dari tipe gadget diikuti nomor antara 1 dan 999. (Wajib)
+ `title` : Judul gadget, biasanya didefinisikan di panel konfigurasi gadget. (Wajib, panjang maksimal 100 karakter)
+ `type` : Tipe gadget, harus sesuai dengan tipe yang diizinkan. (Wajib)
+ `mobile` : Menentukan tampilan gadget di versi mobile. Nilai dapat berupa yes, no, atau only. (Opsional)
+ `locked` : Mengunci gadget sehingga tidak bisa dihapus atau dipindahkan. Nilai dapat berupa true atau false. (Opsional)
+ `cond` : Kondisi eksekusi gadget yang bernilai boolean (true atau false). (Opsional)
+ `visible` : Menentukan visibilitas gadget (true atau false). (Opsional)
+ `version` : Nomor versi gadget, nilai 1 atau 2. (Otomatis)

## Contoh
```xml
<b:widget id='Header1' locked='false' title='Blogger Code (Header)' type='Header' version='2'>...</b:widget>
```
Hasil
```xml
<div class='widget Header' id='Header1' data-version='2'>...</div>
```
