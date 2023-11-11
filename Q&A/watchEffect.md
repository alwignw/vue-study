`watchEffect` adalah salah satu dari beberapa fungsi reaktivitas yang disediakan oleh Vue 3 untuk memantau perubahan dalam dependensi dan secara otomatis mengeksekusi blok efek (effect block) ketika dependensi berubah. Fungsi ini mirip dengan `watch`, tetapi dengan beberapa perbedaan kunci.

Berikut adalah contoh penggunaan `watchEffect`:

```javascript
import { reactive, watchEffect } from 'vue';

const user = reactive({
  name: 'Alice',
  age: 28,
});

watchEffect(() => {
  console.log(`User name: ${user.name}, User age: ${user.age}`);
});
```

Dalam contoh ini, blok efek yang diberikan sebagai argumen untuk `watchEffect` akan dijalankan secara otomatis setiap kali ada perubahan pada properti `user.name` atau `user.age`. Ini memungkinkan Anda untuk menanggapi perubahan dalam dependensi tanpa harus secara eksplisit menyebutkan dependensi mana yang akan diamati.

Beberapa poin kunci tentang `watchEffect`:

1. **Auto-tracking Dependencies**: Vue secara otomatis melacak dependensi dalam blok efek. Jadi, jika ada perubahan pada properti yang digunakan di dalam blok efek, blok efek akan dijalankan ulang.

2. **Tidak Ada Parameter Depan**: Berbeda dengan `watch` yang memerlukan parameter pertama sebagai ekspresi atau fungsi untuk dipantau, `watchEffect` langsung menerima blok efek tanpa memerlukan parameter.

3. **Menanggapi Seluruh Objek**: Jika Anda menggunakan objek reaktif atau ref sebagai dependensi dalam `watchEffect`, itu akan merespons perubahan pada seluruh objek tersebut, bahkan jika hanya satu properti yang diakses di dalam blok efek.

4. **Tidak Mengembalikan Pemutus (Unwatch Function)**: `watchEffect` tidak mengembalikan pemutus (unwatch function) karena blok efek akan terus dieksekusi selama komponen atau tindakan yang mengandungnya masih hidup.

Penggunaan `watchEffect` bermanfaat ketika Anda ingin menanggapi perubahan dalam dependensi tanpa harus menyebutkan dependensi tersebut secara eksplisit. Namun, perlu diingat bahwa karena `watchEffect` tidak mengetahui dependensi mana yang digunakan di dalam blok efek, perlu hati-hati agar tidak mengeksekusi logika yang tidak diinginkan secara berlebihan.