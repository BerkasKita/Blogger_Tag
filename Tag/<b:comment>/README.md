# Penggunaan Tag `<b:comment>` dalam Blogger

Tag `<b:comment>` dalam Blogger adalah tag instruksi XML yang berguna untuk menambahkan komentar dalam kode tema Blogger. Tag ini sangat berguna baik bagi pengembang berpengalaman maupun bagi mereka yang sedang belajar bahasa XML Blogger.

## Sintaks Dasar

Sintaks dasar untuk menggunakan tag `<b:comment>` adalah sebagai berikut:
```
<b:comment>
  KOMENTAR ANDA DI SINI
</b:comment>
```

Tag ini dapat digunakan di seluruh kode XML kecuali di dalam tag `<![CDATA[ ]]>`. Anda dapat menggunakan beberapa tag `<b:comment>`, tetapi tag ini tidak dapat di-nesting.

## Atribut
1. `Render` : Atribut render menentukan apakah komentar harus ditampilkan dalam output HTML. Nilai yang dapat digunakan adalah `true` atau `false`.
2. `expr` : Atribut `expr:render` memungkinkan penggunaan ekspresi Blogger yang dievaluasi menjadi boolean untuk menentukan apakah komentar harus dirender.

## Contoh Penggunaan

### Komentar yang Dirender dalam HTML
```
<b:comment render='true'>
  Komen anda disini.
</b:comment>
```
Hasil: `<!--Komen anda disini.-->`

### Komentar yang tidak Dirender dalam HTML
```
<b:comment render='false'>
  Komen anda disini.
</b:comment>
```
Hasil: Tidak ada/Tidak Tampil

### Komentar Berdasarkan Expression
```
<b:comment render='true'>
  <b:eval expr='data:view.isHomepage ? "Anda dalam halaman utama." : "Anda diluar halaman utama."' />
</b:comment>
```
Hasil jika benar: `<!--Anda dalam halaman utama.-->`
Hasil jika salah: `<!--Anda diluar halaman utama.-->`
