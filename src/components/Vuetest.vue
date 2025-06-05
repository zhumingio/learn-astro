<template>
    <div class="hello" v-for="(item, id) in hello">
        {{ item }}
    </div>
</template>

<script setup>
import { ref, onMounted } from "vue";

const initialHello = ["你好", "Hej", "Hallo", "Hola", "Habari"];
const hello = ref([...initialHello]);

const shuffleArray = () => {
  const array = [...initialHello];
  for (let i = array.length - 1; i > 0; i--) {
    const j = Math.floor(Math.random() * (i + 1));
    [array[i], array[j]] = [array[j], array[i]];
  }
  hello.value = array;
};

onMounted(() => {
  shuffleArray();
});
</script>



<style>
.hello {
    color: #6c06cc;
    font-size: 80px;
}
</style>