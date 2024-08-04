# Penjelasan Tag <b:switch>, <b:case>, dan <b:default> dalam Blogger
## Deskripsi
Tag `<b:switch>`, `<b:case>`, dan `<b:default>` adalah instruksi dalam Blogger yang memungkinkan eksekusi atau non-eksekusi blok kode berdasarkan kondisi tertentu. Tag ini mirip dengan Tag kondisional `<b:if>`, `<b:elseif>`, dan `<b:else>`.

## Sintaks
+ `<b:switch>` + `<b:case>`
  
  ```xml
  <b:switch var='EXPRESSION'>
    <b:case value='VALUE1'/>
    <!-- Dijalankan jika VALUE1 sama dengan hasil dari EXPRESSION -->
    <b:case value='VALUE2'/>
    <!-- Dijalankan jika semua kondisi sebelumnya tidak terpenuhi dan VALUE2 sama dengan hasil dari EXPRESSION -->
  </b:switch>
  ```
+ `<b:switch>` + `<b:case>` + `<b:default>`

  ```xml
  <b:switch var='EXPRESSION'>
    <b:case value='VALUE1'/>
    <!-- Dijalankan jika VALUE1 sama dengan hasil dari EXPRESSION -->
    <b:case value='VALUE2'/>
    <!-- Dijalankan jika semua kondisi sebelumnya tidak terpenuhi dan VALUE2 sama dengan hasil dari EXPRESSION -->
    <b:default/>
    <!-- Dijalankan jika semua kondisi sebelumnya tidak terpenuhi -->
  </b:switch>
  ```

## Atribut
+ `<b:switch>`
  + `var` : Nilai dari switch, bisa berupa data atau ekspresi Blogger. Jenis nilai yang diizinkan adalah string, number, dan boolean.

+ `<b:case>`
  + `value` : Nilai kasus yang dibandingkan dengan nilai switch. Jenis nilai yang diizinkan adalah string, number, dan boolean.
 
+ `<b:default>`
  + Tidak memerlukan atribut.
 
## Contoh
### Data Boolean
```xml
<b:switch var='data:view.isPost'>
  <b:case value='true'/>
  <!-- Dijalankan jika data:view.isPost bernilai true -->
  <b:default/>
  <!-- Dijalankan jika kondisi sebelumnya tidak terpenuhi -->
</b:switch>
```
### Data String
```xml
<b:switch var='data:view.type'>
  <b:case value='item'/>
  <!-- Dijalankan jika data:view.type bernilai "item" -->
  <b:case value='feed'/>
  <!-- Dijalankan jika kondisi sebelumnya tidak terpenuhi dan data:view.type bernilai "feed" -->
  <b:default/>
  <!-- Dijalankan jika semua kondisi sebelumnya tidak terpenuhi -->
</b:switch>
```
### Data Numerik dan Ekspresi Blogger
```xml
<b:switch var='data:posts.length + 10'>
  <b:case value='0'/>
  <!-- Dijalankan jika hasil ekspresi sama dengan 0 -->
  <b:case expr:value='10 - 1'/>
  <!-- Dijalankan jika kondisi sebelumnya tidak terpenuhi dan hasil ekspresi sama dengan 9 -->
  <b:default/>
  <!-- Dijalankan jika semua kondisi sebelumnya tidak terpenuhi -->
</b:switch>
```
