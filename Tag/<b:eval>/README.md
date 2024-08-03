# Penggunaan <b:eval> dalam Blogger

## Deskripsi
Tag `<b:eval`> di Blogger digunakan untuk menampilkan nilai hasil dari ekspresi Blogger secara eksplisit. Tag ini bekerja di seluruh kode XML, kecuali di dalam tag `<![CDATA[`.

## Sintaks
```
<b:eval expr='EKSPRESI'/>
```

## Atribut
+ `expr` : Satu-satunya atribut yang diterima. Nilai yang diharapkan bisa berupa nilai eksplisit, data, atau ekspresi Blogger.

## Contoh Penggunaan

### Mengambil Data dari Indeks Tertentu
```
<b:eval expr='data:posts[0].labels[5].name'/>
```
Hasilnya adalah label ke-6 dari artikel pertama.

### Menggunakan Variabel Tanggal
```
<b:eval expr='format(data:post.date, "EEEE, d MMM YYYY")'/>
```
Hasilnya `Senin, 1 Jan 2024`
