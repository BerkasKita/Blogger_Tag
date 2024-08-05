# Penjelasan Tag <b:widget-settings> dan <b:widget-setting> dalam Blogger
## Deskripsi
Tag `<b:widget-settings>` dan `<b:widget-setting>` dalam Blogger digunakan untuk menyimpan pengaturan gadget yang ditentukan oleh pengguna melalui dashboard Blogger.

## Sintaks
```xml
<b:widget-settings>
  <b:widget-setting name='setting-name'>
    <!-- value setting here -->
  </b:widget-setting>
</b:widget-settings>
```
## Aturan Penggunaan
+ `<b:widget-settings>` harus berada di dalam tag `<b:widget>`.
+ Setiap `<b:widget>` hanya dapat mengandung satu `<b:widget-settings>`.
+ `<b:widget-settings>` hanya dapat mengandung tag `<b:widget-setting>`.
+ Beberapa `<b:widget-setting>` dapat digunakan dalam satu `<b:widget-settings>`.
+ `<b:widget-setting>` hanya boleh mengandung pengaturan gadget.

## Attribut
+ `name` : Nama pengaturan yang merupakan nama yang sudah ditentukan dan tidak dapat dihapus atau diubah.
  ```xml
  <b:widget-setting name='homeTitle'>
    <![CDATA[ ... ]]>
  </b:widget-setting>
  ```
## Fungsi
Tag-tag ini secara otomatis diimplementasikan dalam semua tema Blogger, menyimpan sebagian besar pengaturan yang dilakukan untuk setiap gadget. Hal ini memungkinkan pengguna untuk mengekspor tema ke blog lain tanpa kehilangan data pengaturan

## Modifikasi Nilai
+ Nilai dapat diubah secara manual atau melalui panel konfigurasi gadget.
+ Jika diubah melalui panel konfigurasi, nilai dalam file XML akan diperbarui secara otomatis.
+ Jika diubah langsung dalam XML, mungkin diperlukan penambahan marker CDATA untuk menghindari karakter yang di-escape.
