# Panduan Menggunakan Atribut cond: dalam Blogger
## Deskripsi
`cond:` adalah atribut ekspresi dalam Blogger yang memungkinkan pengguna untuk mendefinisikan kondisi eksekusi. Nilai atribut cond adalah tipe boolean. Atribut ini dirancang untuk menentukan kondisi eksekusi dan dapat dimasukkan dalam beberapa tag Blogger.

## Sintaks
```xml
cond = 'ekspresi'
```
Nilai dari `cond:` adalah boolean yang bisa berupa:
+ Boolean eksplisit: true, false, yes, no
+ Data boolean: Nilai yang mengembalikan true atau false
+ Data apapun: true jika berisi nilai, false jika kosong
+ Ekspresi Blogger: Hasil eksekusi mengembalikan true atau false

## Contoh

### Data Boolean

#### Homepage (Halaman Utama)
```xml
//Versi Baru
cond='data:view.isHomepage'
//Versi Lama
cond='data:blog.url == data:blog.homepageUrl'
```
Tujuan URL : 
+ https://myblog.blogspot.com

#### Halaman Indeks
```xml
//Versi Baru
cond='data:view.isMultipleItems'
//Versi Lama
cond='data:blog.pageType == "index"'
```
Tujuan URL : 
+ https://myblog.blogspot.com
+ https://myblog.blogspot.com/search?q=query
+ https://myblog.blogspot.com/search/label/Blogger
+ https://myblog.blogspot.com/search?label=Blogger
+ https://myblog.blogspot.com/2020

#### Halaman Item (Post dan Page)
```xml
//Versi Baru
cond='data:view.isSingleItem'
//Versi Lama
cond='data:blog.pageType in ["item", "static_page"]'
```
Tujuan URL :
+ https://myblog.blogspot.com/2017/12/tag-blogger.html
+ https://myblog.blogspot.com/p/about.html

#### Halaman Post (Artikel Tunggal)
```xml
//Versi Baru
cond='data:view.isPost'
//Versi Lama
cond='data:blog.pageType == "item"'
```
Tujuan URL :
+ https://myblog.blogspot.com/2017/12/tag-blogger.html

#### Halaman Page (Statis)
```xml
//Versi Baru
cond='data:view.isPage'
//Versi Lama
cond='data:blog.pageType == "static_page"'
```
Tujuan URL :
+ https://myblog.blogspot.com/p/about.html

#### Halaman URL Tertentu
```xml
cond='data:view.url == data:blog.homepageUrl path "/p/about.html"''
```
Tujuan URL :
+ https://myblog.blogspot.com/p/about.html

#### Halaman Label
```xml
//Versi Baru
cond='data:view.isLabelSearch'
//Versi Lama
cond='data:blog.searchLabel'
```
Tujuan URL :
+ https://myblog.blogspot.com/search/label/Blogger
+ https://myblog.blogspot.com/search?label=Blogger

#### Halaman Pencarian
Hanya halaman pencarian berdasarkan query.
```xml
cond='data:view.isSearch and !data:view.isLabelSearch'
```
Tujuan URL :
+ https://myblog.blogspot.com/search?q=query
Termasuk halaman pencarian label (semua yang mengandung kata "search" di URL)
```xml
//Versi Baru
cond='data:view.isSearch'
//Versi Lama
cond='data:blog.searchQuery'
```
Tujuan URL :
+ https://myblog.blogspot.com/search?q=query
+ https://myblog.blogspot.com/search/label/Blogger
+ https://myblog.blogspot.com/search?label=Blogger

#### Halaman Arsip
```xml
//Versi Baru
cond='data:view.isArchive'
//Versi Lama
cond='data:blog.pageType == "archive"'
```
Tujuan URL :
+ https://myblog.blogspot.com/2020
+ https://myblog.blogspot.com/2020/04
+ https://myblog.blogspot.com/2020_04_14_archive.html

#### Halaman Error 404 (Page Not Found)
```xml
//Versi Baru
cond='data:view.isError'
//Versi Lama
cond='data:blog.pageType == "error_page"'
```
Tujuan URL :
+ https://myblog.blogspot.com/404.html

#### Halaman Mobile
```xml
cond='data:blog.isMobileRequest'
```
Tujuan URL :
+ https://myblog.blogspot.com?m=1

#### Halaman Pratinjau (Preview)
```xml
cond='data:view.isPreview'
```

#### Halaman Edit Layout di Dashboard
```xml
cond='data:view.isLayoutMode'
```

## Ekspresi Boolean
Tag kondisional Blogger juga bisa menggunakan NOT, AND, atau OR.

+ NOT:
  Kondisi jika bukan halaman yang dimaksud. Tambahkan tanda seru `!`.
  
  ```xml
  cond='!data:view.isPost'
  ```
+ AND:
  Kondisi jika keduanya benar. Tambahkan `AND`.
  
  ```xml
  cond='!data:view.isPost and data:view.isMultipleItems'
  ```
+ OR:
  Kondisi jika salah satunya benar. Tambahkan `OR`
  
  ```xml
  cond='data:view.isPost or data:view.isMultipleItems'
  ```
