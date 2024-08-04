# Penjelasan Tag <b:skin> dan <b:template-skin> dalam Blogger

## Deskripsi Tag
Tag `<b:skin>` dan `<b:template-skin>` digunakan dalam header file XML tema Blogger. Keduanya berisi deklarasi variabel dan CSS yang berinteraksi dengan alat pembuat tema.


- **`<b:skin>`** : Mengandung mayoritas CSS blog.
- **`<b:template-skin>`** : Digunakan untuk mendefinisikan CSS di tab "Tata Letak" di dashboard Blogger.

## Sintaksis

- **`<b:skin>`** :
  ```xml
  <b:skin><![CDATA[...]]></b:skin>
  ```
- **`<b:template-skin>`** :
  ```xml
  <b:template-skin><![CDATA[...]]></b:template-skin>
  ```
## Aturan Penggunaan
+ Tag `<b:skin>` wajib ada di setiap tema.
+ Tag `<b:template-skin>` tidak diizinkan dalam tema Versi 1.
+ Keduanya tidak boleh bersarang dan harus berada di antara tag `<head>` dan `</head>`.
+ Hanya dapat mengandung deklarasi CSS dan variabel.

## Dressing variables
Bagian ini mendefinisikan variabel yang memungkinkan admin blog untuk mengkustomisasi tema tanpa pengetahuan CSS. Variabel ini didefinisikan dalam editor XML dan digunakan dalam alat pembuat tema untuk mengatur berbagai elemen seperti latar belakang, tema, lebar kolom, dan lainnya.

### Sintaksis Deklarasi Variabel
+ Tag `<Group>` untuk mengelompokkan beberapa variabel.
  ```xml
  <Group description="description" selector="selector HTML">...</Group>
  ```
+ Tag `<Variable>` mendefinisikan variabel dengan atribut berikut.
  ```xml
  <Variable name="name" description="description" type="type" default="value" value="value"/>
  ```
### Atribut yang Digunakan
+ `description` : Deskripsi singkat grup atau variabel.
+ `selector` : Elemen HTML atau kelas CSS yang ditargetkan.
+ `name` : Nama unik variabel, hanya mengandung huruf atau angka.
+ `type` : Jenis variabel, seperti color, length, font.
+ `default` : Nilai default variabel.
+ `value` : Nilai saat ini dari variabel.

### Jenis Variabel
+ `color` : Mengatur warna dengan kode hex, RGB, atau RGBA.
+ `length` : Mengatur ukuran dalam px.
+ `font` : Mengatur jenis dan ukuran font.

### Contoh Atribut
+ color:
  + `red` : Nilai RGB merah (0-255).
  + `green` : Nilai RGB hijau (0-255).
  + `blue` : Nilai RGB biru (0-255).
  + `alpha` : Transparansi (0.0-1.0).
+ font:
  + `family` : Nama font.
  + `size` : Ukuran font.
+ length:
  + `min` : Nilai minimum.
  + `max` : Nilai maksimum.
+ hideEditor: Mengatur apakah form variabel ditampilkan (true atau false).
