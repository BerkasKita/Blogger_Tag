# Penjelasan Tag <b:section> dalam Blogger

## Deskripsi
Tag `<b:section>` dalam Blogger adalah elemen tata letak yang digunakan untuk menampung gadget Blogger. Tag ini harus diletakkan di antara tag `<body></body>` dalam struktur XML tema Blogger. Tag `<b:section>` hanya dapat berisi tag `<b:widget>` dan tidak dapat diimbuhkan.

## Sintaks
```xml
<b:section cond='TRUE|FALSE' name='section_name' preferred='YES|NO|TRUE|FALSE' class='class_name' id='id_name' maxwidgets='number' showaddelement='YES|NO|TRUE|FALSE'></b:section>
```
## Aturan
+ Setiap tema harus memiliki setidaknya satu tag `<b:section>`.
+ Salah satu `<b:section>` harus memiliki atribut `preferred='true'`.

## Atribut
Beberapa atribut dapat ditambahkan ke dalam tag `<b:section>`, baik yang wajib maupun opsional
<table>
  <thead>
    <tr>
      <th>Atribut</th>
      <th>Deskripsi</th>
      <th>Klasifikasi</th>
      <th>Prefiks "expr:"</th>
      <th>Implementasi</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>ads</code></td>
      <td>Menentukan apakah section ini khusus untuk iklan AdSense (true/false).</td>
      <td>HTML klasik</td>
      <td>Tidak Diizinkan</td>
      <td>Opsional</td>
    </tr>
    <tr>
      <td><code>id</code></td>
      <td>ID unik untuk section.</td>
      <td>HTML klasik</td>
      <td>Tidak Diizinkan</td>
      <td>Wajib</td>
    </tr>
    <tr>
      <td><code>class</code></td>
      <td>Kelas untuk section.</td>
      <td>HTML klasik</td>
      <td>Tidak Diizinkan</td>
      <td>Opsional</td>
    </tr>
    <tr>
      <td><code>name</code></td>
      <td>Nama untuk section, jika tidak ada, nilai atribut <code>id</code> akan digunakan.</td>
      <td>HTML klasik</td>
      <td>Diizinkan</td>
      <td>Opsional</td>
    </tr>
    <tr>
      <td><code>maxwidgets</code></td>
      <td>Jumlah maksimum gadget yang dapat dimuat dalam section.</td>
      <td>HTML klasik</td>
      <td>Tidak Diizinkan</td>
      <td>Opsional</td>
    </tr>
    <tr>
      <td><code>preferred</code></td>
      <td>Menentukan apakah ini section utama blog (yes/no).</td>
      <td>HTML klasik</td>
      <td>Tidak Diizinkan</td>
      <td>Opsional</td>
    </tr>
    <tr>
      <td><code>showaddelement</code></td>
      <td>Menentukan apakah link "Tambah gadget" ditampilkan (yes/true).</td>
      <td>HTML klasik</td>
      <td>Tidak Diizinkan</td>
      <td>Opsional</td>
    </tr>
    <tr>
      <td><code>cond</code></td>
      <td>Kondisi untuk eksekusi section, bisa berupa nilai boolean (true/false) atau ekspresi Blogger.</td>
      <td>XML Blogger</td>
      <td>Diizinkan</td>
      <td>Opsional</td>
    </tr>
  </tbody>
</table>

## Contoh
```xml
<b:section class='header' id='header' name='Thema_Header' showaddelement='yes'>...</b:section>
```
Hasil HTML
Setelah analisis file XML, tag `<b:section>` dikonversi menjadi tag `<div>`
```xml
<div class='header section' id='header' name='Thema_Header'>...</div>
```
+ Atribut `class`, `id`, dan `name` akan disertakan dalam tag `<div>` jika disebutkan dalam XML.
+ Nilai `section` otomatis ditambahkan ke dalam atribut class.
+ Nilai `no-items` otomatis ditambahkan ke atribut `class` jika section tidak ada widget yang terlihat.
