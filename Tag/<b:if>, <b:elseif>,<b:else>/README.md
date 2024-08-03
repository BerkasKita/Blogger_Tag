# Penjelasan dan Contoh Penggunaan <b:if>, <b:elseif>, <b:else> dalam Blogger

## Deskripsi
Tag kondisional dalam Blogger meliputi <b:if>, <b:elseif>, dan <b:else>. Tag ini digunakan untuk mengeksekusi atau tidak mengeksekusi blok kode dalam editor XML Blogger berdasarkan kondisi yang diberikan.

### Sintaks

- ```xml
  <b:if cond = 'CONDITION'>
    ...
  </b:if>
  ```
- ```xml
  <b:if cond = 'CONDITION'>
    ...
  <b:else/>
    ...
  </b:if>
  ```

- ```xml
  <b:if cond = 'CONDITION1'>
    ...
  <b:elseif cond = 'CONDITION2'/>
    ...
  </b:if>
  ```
- ```xml
  <b:if cond = 'CONDITION1'>
    ...
  <b:elseif cond = 'CONDITION2'/>
    ...
  <b:else/>
    ...
  </b:if>
  ```

## Contoh Penggunaan
### Kode dengan Satu Kondisi
```xml
<b:if cond='CONDITION'>
  <!-- Blok kode ini akan dieksekusi jika kondisi benar -->
</b:if>
```
### Kode dengan Dua Kondisi
```xml
<b:if cond='CONDITION'>
   <!-- Kode dieksekusi jika kondisi bernilai true -->
 <b:else/>
   <!-- Kode dieksekusi jika kondisi bernilai false -->
</b:if>
```
### Kode dengan Dua Kondisi dan Pengecualian
```xml
<b:if cond='CONDITION1'>
   <!-- Kode dieksekusi jika kondisi 1 bernilai true -->
 <b:elseif cond='CONDITION2'/>
   <!-- Kode dieksekusi jika kondisi 1 bernilai false dan kondisi 2 bernilai true -->
 <b:else/>
   <!-- Kode dieksekusi jika kondisi 1 dan 2 bernilai false -->
</b:if>
```
## Aturan Penggunaan
+ Tag `<b:if>`, `<b:elseif>`, dan `<b:else>` dapat digunakan di seluruh kode XML, kecuali di dalam tag `<![CDATA[`.
+ Tag `<b:elseif>` dan `<b:else>` harus berada di dalam tag `<b:if>`.
+ Penggunaan tag `<b:elseif>` dan `<b:else>` bersifat opsional.
+ Tag `<b:elseif>` dapat digunakan beberapa kali dalam tag `<b:if>`, tetapi `<b:else>` hanya dapat digunakan sekali.
+ Jika `<b:if>` mengandung beberapa `<b:elseif>`, maka `<b:else>` harus menjadi tag kondisi terakhir.

## Atribut
+ `cond` : Atribut ini menentukan kondisi untuk eksekusi blok kode anak. Nilai yang diharapkan adalah boolean (true atau false). Dapat berupa nilai eksplisit, data, atau ekspresi Blogger.

## Contoh Penggunaan
### Dengan Data Boolean
```xml
<b:if cond='data:view.isPost'>
  ...
</b:if>
```
### Dengan Data String
```xml
<b:if cond='data:view.title'>
  ...
</b:if>
```
### Dengan Operasi Perbandingan
```xml
<b:if cond='data:view.type == "item"'>
  ...
</b:if>
```
### Dengan Operasi Logika
```xml
<b:if cond='data:view.search.label and data:view.isMobile'>
  ...
</b:if>
```

