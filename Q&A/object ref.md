Objek `ref` adalah cara lain untuk mengatasi reaktivitas dalam Vue.js. Sama seperti objek reaktif, objek `ref` digunakan untuk membuat nilai yang reaktif, tetapi dengan fokus pada satu nilai tunggal, bukan seluruh objek. Objek `ref` memberikan referensi ke nilai, dan perubahan pada nilai tersebut akan memicu re-rendering secara otomatis.

Berikut adalah contoh penggunaan objek `ref`:

```javascript
import { ref } from 'vue';

const age = ref(25);
```

Dalam contoh ini, `age` adalah objek `ref` yang menyimpan nilai awal 25. Ketika nilai `age` diubah, misalnya dengan `age.value = 30`, sistem reaktivitas Vue akan mendeteksi perubahan dan memicu pembaruan tampilan yang terkait.

Perlu diperhatikan bahwa untuk mengakses nilai yang disimpan dalam objek `ref`, kita menggunakan properti `.value`. Contohnya, `age.value` untuk mendapatkan nilai dari objek `ref` `age`.

Objek `ref` berguna ketika Anda hanya perlu mengelola satu nilai reaktif atau saat Anda ingin mengonversi nilai non-reaktif menjadi nilai reaktif. Jika Anda memiliki objek kompleks dengan banyak properti yang perlu dipantau, menggunakan objek reaktif dengan `reactive` mungkin lebih sesuai.

Namun, baik objek `ref` maupun objek reaktif (`reactive`) adalah bagian dari alat reaktivitas Vue.js yang memudahkan pengelolaan dan pemantauan perubahan data dalam aplikasi Vue.