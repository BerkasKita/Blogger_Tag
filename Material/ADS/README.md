# Menambahkan tempat iklan antara artikel
menambahkan tempat iklan di antara artikel-artikel di Blogger menggunakan sintaks xml.

## Sintaks
Gunakan sintaks berikut untuk menempatkan iklan di antara artikel
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
   + `number` harus berupa angka (0, 1, 2, ...).
   + Jika number melebihi jumlah total artikel, iklan tidak akan muncul.

## Langkah Implementasi:
1. Cari `<b:includable id='postCommentsAndAd' var='post'>` jika masih menggunakan versi bawaan (Original).
   ```xml
   <b:includable id='postCommentsAndAd' var='post'>
    <article class='post-outer-container'>...</article>
  
    <!-- Show ad outside post container (between posts) for feed pages. -->
    <b:include cond='data:view.isMultipleItems and data:post.includeAd' data='post' name='inlineAd'/>
   </b:includable>
   ```
3. Sisipkan kode yang diberikan di atas baris `<article class='post-outer-container'>...</article>`.
   Contoh implementasi iklan:
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
4. Menambahkan lebih dari 1 tempat iklan

   Untuk menambahkan beberapa iklan, ulangi sintaks dengan nilai number yang berbeda untuk posisi yang berbeda
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
