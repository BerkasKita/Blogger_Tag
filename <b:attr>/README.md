# Panduan Penggunaan Tag `<b:attr>` dalam Blogger

## Deskripsi
Tag `<b:attr>` dalam Blogger digunakan untuk menambahkan atribut ke tag induk dalam kode XML tema Blogger. Tag ini sangat fleksibel dan dapat digunakan dengan berbagai kondisi dan nilai.

## Sintaks
```
<div>
  <b:attr cond='KONDISI' name='NAMA_ATRIBUT' value='NILAI' />
</div>
```

## Atribut
+ `name` : Menentukan nama atribut yang akan ditambahkan (wajib).
+ `value` : Menentukan nilai dari atribut (wajib).
+ `cond` : Kondisi boolean yang menentukan apakah atribut akan ditambahkan (opsional).
