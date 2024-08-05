# Penjelasan Tag <b:tag> dalam Blogger
## Deskripsi
`<b:tag>` adalah tag instruksi XML yang memungkinkan penambahan tag HTML apapun dalam kode XML Blogger. Tag ini bekerja di seluruh kode XML, kecuali di dalam penandaan `<![CDATA[...]]>`.

## Sintaks
```xml
<b:tag cond='CONDITION' name='TAG_NAME'>...</b:tag>
<b:tag cond='CONDITION' expr:name='EXPRESSION'>...</b:tag>
```

## Atribut
Tag `<b:tag>` dapat memiliki beberapa atribut, beberapa di antaranya wajib:
+ `name` : Nama tag HTML yang akan dibuat. Dapat berupa string atau ekspresi Blogger yang hasilnya string. Wajib.
+ `cond` : Kondisi eksekusi tag. Nilainya harus boolean (true atau false). Opsional.
+ `class` , `id` , `dll` .: Semua atribut standar HTML (kecuali name). Opsional.

## Contoh
+ Menambahkan Tag `<div>`
  ```xml
  <b:tag name='div'>...</b:tag>
  ```
  Hasil
  
  ```html
  <div>...</div>
  ```
+ Tag dengan Kondisi
  ```xml
  <b:tag cond='data:view.isHomepage' name='div'>...</b:tag>
  ```
  Hasil jika kondisi benar
  
  ```html
  <div>...</div>
  ```
+ Tag dengan Nama Dinamis
  ```xml
  <b:tag expr:name='data:view.isHomepage ? "div" : "span"'>...</b:tag>
  ```
  Hasil jika kondisi benar
  
  ```html
  <div>...</div>
  ```
  Hasil jika kondisi salah
  
  ```html
  <span>...</span>
  ```
