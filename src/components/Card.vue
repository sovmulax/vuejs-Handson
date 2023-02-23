<script setup>
import { ref } from "vue";
const props = defineProps(["note", "notes"]);

console.log(props.notes)
</script>

<template>
  <div class="cards-container">
  <br><br>
    <div v-for="note in notes">
    <div class="card" :style="{ backgroundColor: note.color }">
      <h5 class="main-text">{{ note.titre }}</h5>
      <p class="main-text">{{ note.description }}</p>
      <p class="date">{{ note.date.toLocaleDateString("en-US") }}</p>
    </div>
  </div>
  </div>
</template>

<style scoped>
.card {
  width: 225px;
  height: 225px;
  background-color: rgb(237, 182, 44);
  padding: 10px;
  border-radius: 15px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin-right: 20px;
  margin-bottom: 20px;
}
.main-text {
  line-height: 1.25;
  font-size: 17.5px;
  font-weight: bold;
}
.date {
  font-size: 12.5px;
  margin-top: auto;
}
.cards-container {
  display: flex;
  flex-wrap: wrap;
}
</style>
