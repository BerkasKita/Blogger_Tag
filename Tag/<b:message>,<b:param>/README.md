# Panduan Penggunaan Tag `<b:message>` dan `<b:param>` dalam Blogger

## Deskripsi
Tag `<b:message>` dan `<b:param>` digunakan dalam kode XML Blogger untuk menampilkan nilai data tipe pesan dan menyertakan nilai tambahan ke dalam pesan tersebut.

## Syntax
```xml
<b:message name='ALIAS_MESSAGE'>
  <b:param name='PARAM_NAME' value='PARAM_VALUE' />
</b:message>
```
+ `name` : Nama alias dari data tipe pesan.
+ `<b:param>` : Menambahkan elemen ke pesan dengan atribut name dan value.

## Aturan Penggunaan
+ Tag <b:message> tidak dapat disarangkan.
+ Satu atau lebih tag <b:param> harus disertakan dalam tag <b:message>.
+ Tag <b:param> hanya diperlukan untuk sejumlah data tipe pesan yang terbatas.

## Atribut
+ `<b:message>`
  + `name` : Alias dari data tipe pesan. Contoh: messages.authorSaid.
+ `<b:param>`
  + `name` : Nama parameter. Nilai ini adalah nama yang sudah ditentukan.
  + `value` : Nilai yang akan ditambahkan ke pesan. Bisa berupa data atau expression jika diawali dengan `expr:`.
 
## Contoh
```xml
<b:message name='messages.home' />
```
Hasil `Home`
