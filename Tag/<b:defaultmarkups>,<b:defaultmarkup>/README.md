# Panduan Penggunaan `<b:defaultmarkups>` dan `<b:defaultmarkup>` di Blogger

Dokumen ini memberikan informasi terperinci tentang penggunaan tag `<b:defaultmarkups>` dan `<b:defaultmarkup>` di Blogger. Tag-tag ini memungkinkan pengembang untuk mendefinisikan penyertaan widget default yang spesifik untuk tema Blogger. Tujuan utamanya adalah untuk mempermudah proses pengembangan tema dan widget dengan menyediakan metode standar untuk menyertakan potongan kode default.

## Penjelasan Tag

### `<b:defaultmarkups>`
Tag ini sebaiknya ditempatkan sebelum `</head>` atau `</body>`. Tag ini hanya dapat berisi tag `<b:defaultmarkup>`.

### `<b:defaultmarkup>`
Tag ini berisi penyertaan untuk widget tertentu, yang didefinisikan oleh atribut `type` (misalnya, 'Profile', 'Blog'). Tag ini hanya dapat menyertakan tag `<b:includable>`.

## Atribut yang Digunakan


- `type`: Menentukan jenis widget. Atribut ini wajib dan tidak mendukung prefiks `expr:`.

## Fungsi


- Tag ini terutama digunakan oleh pengembang tema atau widget untuk membuat model default untuk widget yang spesifik untuk suatu tema.
- Ketika widget diinstal atau direset, penyertaan yang didefinisikan dalam `<b:defaultmarkup>` secara otomatis ditambahkan ke kode widget.

- Pengembang dapat membuat penyertaan baru atau menimpa yang sudah ada dengan menggunakan ID mereka.

## Contoh Penggunaan

### Widget Tunggal
```
<b:defaultmarkups>
  <b:defaultmarkup type='Profile'>
    <b:includable id='main'>
      <!-- Kode default untuk 'main' di widget 'Profile' -->
    </b:includable>
  </b:defaultmarkup>
</b:defaultmarkups>
```

### Beberapa Widget
```
<b:defaultmarkups>
  <b:defaultmarkup type='Blog, FeaturedPost, PopularPosts'>
    <b:includable id='main'>
      <!-- Kode default untuk 'main' di widget 'Blog', 'FeaturedPost', 'PopularPosts' -->
    </b:includable>
  </b:defaultmarkup>
</b:defaultmarkups>
```

### Beberapa Penyertaan dalam Satu Widget
```
<b:defaultmarkups>
  <b:defaultmarkup type='Blog'>
    <b:includable id='main'>
      <!-- Kode default untuk 'main' di widget 'Blog' -->
    </b:includable>
    <b:includable id='title'>
      <!-- Penyertaan default baru 'title' di widget 'Blog' -->
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
