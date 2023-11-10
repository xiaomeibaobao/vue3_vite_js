<script setup>
  import { ref, reactive } from 'vue';
  const count = ref(0)
  const obj = ref({ a: 1 })
  const obj1 = reactive({ a: 1 })
  const rawHtml = ref("<span style='color: red;'>This should be red.</span>")
  const row = {}
  const proxy = reactive(row)
  console.log(row === proxy);
  console.log(obj.value)
  console.log(obj1)
  function reduce() {
    count.value--
  }
  function add() {
    count.value++
  }
</script>

<template>
  <div class="about">
    <div>计数：<button @click="reduce">-</button>{{ count }}<button @click="add">+</button></div>
    <p v-html="rawHtml"></p>
    <p>{{ rawHtml }}</p>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
    flex-direction: row;
    flex-wrap: wrap;
  }
}
</style>
