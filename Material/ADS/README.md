# Menambahkan tempat iklan antara artikel

## Syntax
```xml
<b:if cond='data:i == number'>
  <article class='post-outer-container pin'>
    <div class='ADS'>
      ADS Is Here
    </div>
  </article>
</b:if>
```
## Aturan Penggunaan
   + `number` : posisi atau letak penempatanan (Wajib).
   + `number` : isi dengan angka (0,1,2,3,...) dan seperti array angka pertama diawali angka `0` bukan angka `1`, seperti 0 untuk artikel pertama, 1 untuk artikel kedua dan seterusmya.
   + `number` : jika lebih besar dari jumlah artikel maka tidak akan tampil.

## Pemasangan
1. Cari `<b:includable id='postCommentsAndAd' var='post'>` jika masih menggunakan versi bawaan (Original).
   ```xml
   <b:includable id='postCommentsAndAd' var='post'>
    <article class='post-outer-container'>...</article>
  
    <!-- Show ad outside post container (between posts) for feed pages. -->
    <b:include cond='data:view.isMultipleItems and data:post.includeAd' data='post' name='inlineAd'/>
   </b:includable>
   ```
3. Tempel kode ini diatas `<article class='post-outer-container'>...</article>`.
   ```xml
   <b:if cond='!data:view.isSingleItem'>
    <b:if cond='data:i == 0'>
      <article class='post-outer-container pin'>
        <div class='ADS'>
          ADS Is Here
        </div>
      </article>
    </b:if>
   </b:if>
   ```
   dan hasilnya seperti ini
   
   ```xml
   <b:includable id='postCommentsAndAd' var='post'>
    <b:if cond='!data:view.isSingleItem'>
      <b:if cond='data:i == 0'>
        <article class='post-outer-container ADS'>
          <div class='ADS'>
            ADS Is Here
          </div>
        </article>
      </b:if>
    </b:if>
    <article class='post-outer-container'>...</article>
  
    <!-- Show ad outside post container (between posts) for feed pages. -->
    <b:include cond='data:view.isMultipleItems and data:post.includeAd' data='post' name='inlineAd'/>
   </b:includable>
   ```
   
    jika ingin menambah tempat iklan lagi, tinggal buat Syntax baru
    ```xml
    <b:if cond='!data:view.isSingleItem'>
      <b:if cond='data:i == 0'>
        <article class='post-outer-container ADS'>
          <div class='ADS'>
            Iklan 1
          </div>
        </article>
      </b:if>
      <b:if cond='data:i == 4'>
        <article class='post-outer-container ADS'>
          <div class='ADS'>
            Iklan ke 5
          </div>
        </article>
      </b:if>
      <b:if cond='data:i == 10'>
        <article class='post-outer-container ADS'>
          <div class='ADS'>
            Iklan ke 11
          </div>
        </article>
      </b:if>
      ...
    </b:if>
    ```
