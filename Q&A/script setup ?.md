`<script setup>` adalah sintaks eksperimental yang diperkenalkan dalam Vue 3 untuk menyederhanakan struktur komponen dengan memisahkan logika dari template dan meningkatkan produktivitas pengembangan. Sintaks ini dirancang untuk menggantikan konvensi penggunaan `<script>`, `<template>`, dan `<style>` dalam komponen Vue tradisional.

Dengan `<script setup>`, Anda dapat menulis logika komponen Vue dalam satu blok `<script>` dan mengakses data, props, dan lainnya tanpa perlu menyatakan variabel atau fungsi secara eksplisit. Sintaks ini dapat membuat kode komponen menjadi lebih ringkas dan mudah dibaca.

Contoh penggunaan `<script setup>`:

```vue
<template>
  <div>
    <p>{{ message }}</p>
    <button @click="increaseCount">Increase Count</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const message = ref('Hello, Vue!');
const count = ref(0);

const increaseCount = () => {
  count.value++;
};
</script>
```

Dalam contoh ini, blok `<script setup>` mencakup logika komponen. Variabel `message` dan `count` bersifat reaktif dan dapat digunakan langsung dalam template tanpa harus menyatakan mereka secara eksplisit. Fungsi `increaseCount` juga dapat diakses langsung dari template.

Perlu dicatat bahwa `<script setup>` masih eksperimental dan mungkin mengalami perubahan atau peningkatan dalam versi Vue yang akan datang. Meskipun demikian, penggunaan `<script setup>` dapat menjadi pilihan yang baik untuk mengurangi boilerplate code dalam komponen Vue dan membuat kode lebih bersih.