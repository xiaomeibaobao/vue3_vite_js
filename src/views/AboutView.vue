<script setup>
  import { ref, reactive, computed } from 'vue';
  const author = reactive({
    name: 'xiaomei',
    books: [
      'vue2 - advanced Guide',
      'vue3 - Basis Guide',
      'Vue4 - The Mystery'
    ]
  })

  const publishedBooksMessage = computed(() => {
    return author.books.length ? 'Yes' : 'No'
  })

  const count = ref(0)
  const obj = ref({ a: 1 })
  const obj1 = reactive({ a: 1 })
  const rawHtml = ref("<span style='color: red;'>This should be red.</span>")
  const row = {}
  const proxy = reactive(row)
  const test = ref(0)
  const state = reactive({
    test
  })
  const next_test = ref(3)
  state.test = next_test
  state.test++
  console.log(next_test.value);
  console.log(state);
  console.log(test.value);

  const return_red = ref(true)
  const font_big = ref(true)
  const arr = reactive(['book', 'game', 'sport', 'study', 'play'])
  const class_obj = computed(() => {
    return {
      red: return_red.value,
      font: font_big.value
    }
  })
  function reduce() {
    count.value--
  }
  function add() {
    count.value++
  }

  function reduceBook() {
    author.books.shift()
  }

  function addBook() {
    author.books.push('vue n - test -text!')
  }

  function changeFont() {
    font_big.value = !font_big.value
    return_red.value = !return_red.value
  }
</script>

<template>
  <div class="about">
    <div>计数：<button @click="reduce">-</button>{{ count }}<button @click="add">+</button></div>
    <p v-html="rawHtml"></p>
    <p>{{ rawHtml }}</p>
    <p><button @click="reduceBook">-</button>{{publishedBooksMessage}}<button @click="addBook">+</button></p>
    <span :class="class_obj">变红变大</span>
    <button @click="changeFont">改变字体</button>
    <ul>
      <li v-for="(item, idx) in arr" :key="idx">{{ item }}</li>
    </ul>
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
  .red {
    color: red;
  }

  .font {
    font-size: 20px;
  }
}
</style>
