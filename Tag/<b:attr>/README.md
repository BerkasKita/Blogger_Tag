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

## Contoh

### Menambahkan ID
```
<div>
  <b:attr name='id' value='ILOVEBLOGGER' />
</div>
```
Hasil: `<div id='ILOVEBLOGGER'></div>`

### Atribut Kondisional
```
<div>
  <b:attr cond='data:view.isHomepage' name='style' value='background: transparent' />
</div>
```
Hasil jika benar: `<div style='background: transparent'></div>`
Hasil jika salah: `<div></div>`

### Atribut dengan Ekspresi
```
<a>
  <b:attr name='href' expr:value='data:blog.homepageUrl path "/search/" params { label: "TOTO" }' />
  LINK
</a>
```
Hasil: `<a href='https://BLOG_NAME.blogspot.com/search?label=TOTO'>LINK</a>`

### Beberapa Atribut
```
<a>
  <b:attr name='href' expr:value='data:view.url' />
  <b:attr name='target' value='_blank' />
  <b:attr name='title' expr:value='data:view.title' />
  LINK
</a>
```
Hasil: `<a href='https://BLOG_NAME.blogspot.com/' target='_blank' title='PAGE_TITLE'>LINK</a>`
