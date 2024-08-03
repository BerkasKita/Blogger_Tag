# Panduan Penggunaan `<b:defaultmarkups>` dan `<b:defaultmarkup>` di Blogger

Dokumen ini memberikan informasi terperinci tentang penggunaan tag `<b:defaultmarkups>` dan `<b:defaultmarkup>` di Blogger. Tag-tag ini memungkinkan pengembang untuk mendefinisikan penyertaan gadget default yang spesifik untuk tema Blogger. Tujuan utamanya adalah untuk mempermudah proses pengembangan tema dan gadget dengan menyediakan metode standar untuk menyertakan potongan kode default.

## Penjelasan Tag

### `<b:defaultmarkups>`
Tag ini sebaiknya ditempatkan sebelum `</head>` atau `</body>`. Tag ini hanya dapat berisi tag `<b:defaultmarkup>`.

### `<b:defaultmarkup>`
Tag ini berisi penyertaan untuk gadget tertentu, yang didefinisikan oleh atribut `type` (misalnya, 'Profile', 'Blog'). Tag ini hanya dapat menyertakan tag `<b:includable>`.

## Atribut yang Digunakan


- `type`: Menentukan jenis gadget. Atribut ini wajib dan tidak mendukung prefiks `expr:`.

## Fungsi


- Tag ini terutama digunakan oleh pengembang tema atau gadget untuk membuat model default untuk gadget yang spesifik untuk suatu tema.
- Ketika gadget diinstal atau direset, penyertaan yang didefinisikan dalam `<b:defaultmarkup>` secara otomatis ditambahkan ke kode gadget.

- Pengembang dapat membuat penyertaan baru atau menimpa yang sudah ada dengan menggunakan ID mereka.

## Contoh Penggunaan

### Gadget Tunggal
```
<b:defaultmarkups>
  <b:defaultmarkup type='Profile'>
    <b:includable id='main'>
      <!-- Kode default untuk 'main' di gadget 'Profile' -->
    </b:includable>
  </b:defaultmarkup>
</b:defaultmarkups>
```

### Beberapa Gadget
```
<b:defaultmarkups>
  <b:defaultmarkup type='Blog, FeaturedPost, PopularPosts'>
    <b:includable id='main'>
      <!-- Kode default untuk 'main' di gadget 'Blog', 'FeaturedPost', 'PopularPosts' -->
    </b:includable>
  </b:defaultmarkup>
</b:defaultmarkups>
```

### Beberapa Penyertaan dalam Satu Gadget
```
<b:defaultmarkups>
  <b:defaultmarkup type='Blog'>
    <b:includable id='main'>
      <!-- Kode default untuk 'main' di gadget 'Blog' -->
    </b:includable>
    <b:includable id='title'>
      <!-- Penyertaan default baru 'title' di gadget 'Blog' -->
    </b:includable>
  </b:defaultmarkup>
</b:defaultmarkups>
```

### Membuat Penyertaan Umum
```
<b:defaultmarkups>
  <b:defaultmarkup type='Common'>
    <b:includable id='MyMetaTags'>
      <!-- Pembuatan penyertaan umum baru -->
    </b:includable>
  </b:defaultmarkup>
</b:defaultmarkups>
```
