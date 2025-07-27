<script setup>
// imports
import q from "./data/quizes.json";
import { ref, watch } from 'vue';

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
        <div class="card" v-for="quiz in quizes" :key="quiz.id">
          <img :src="quiz.img" :alt="quiz.name">
          <div class="card-text">
            <h2>{{ quiz.name }}</h2>
            <p class="desc">{{ quiz.questions.length }} question</p>
          </div><!--./card-text-->
        </div><!--./card-->
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

.card {
  width: 310px;

  margin: 0 20px 0 35px;
  border-radius: 2%;

  box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  cursor: pointer;
}

.card img {
  width: 100%;
  height: 190px;
  margin: 0;
}

.card .card-text {
  padding: 0 5px;
}

.card .card-text h2 {
  font-weight: bold;
}
</style>
