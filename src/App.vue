<script setup>
// imports
import q from "./data/quizes.json";
import { ref, watch } from 'vue';
import Card from "./components/Card.vue"

// cons & vars
const quizes = ref(q);
const search = ref("");

// watch
watch(search, () =>
  quizes.value = q.filter(
    quiz => quiz.name.toLowerCase().includes(search.value.toLocaleLowerCase())
  )
);
</script>

<template>
  <div>
    <div class="container">
      <header>
        <h1>Quizes</h1>
        <input v-model.trim="search" type="text" placeholder="search...">
      </header><!--./header-->

      <div class="options-container">
        <Card v-for="quiz in quizes" :key="quiz.id" />
      </div><!--./options-container-->
    </div><!--./container-->
  </div>
</template>

<style scoped>
.container {
  max-width: 1000px;
  margin: 0 auto;
}

header {
  display: flex;
  align-items: center;
  margin: 10px 0 30px 0;
}

header h1 {
  font-weight: bold;
  margin-right: 30px;
}

header input {
  border: none;
  padding: 10px;
  border-radius: 5px;

  background-color: rgba(128, 128, 128, 0.1);
}

.options-container {
  display: flex;
  flex-wrap: wrap;

  margin-top: 40px;
}
</style>
