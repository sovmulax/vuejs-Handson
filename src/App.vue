<script setup>
import { ref } from "vue";
import Card from "./components/Card.vue";
import Modal from "./components/Modal.vue";

const isShow = ref(false);
const notes = ref([]);

const show = () => {
  isShow.value = !isShow.value;
  console.log(isShow.value);
};

function getRandomColor() {
  const color = "hsl(" + Math.random() * 360 + ", 100%, 75%)";
  return color;
}

notes.value.push({
  id: Math.floor(Math.random() * 100000),
  titre: "titre",
  description: "description",
  color: getRandomColor(),
  date: new Date(),
});

const addnote = (titre, description) => {
  notes.value.push({
    id: Math.floor(Math.random() * 100000),
    titre: titre,
    description: description,
    color: getRandomColor(),
    date: new Date(),
  });
  isShow.value = !isShow.value;
};
</script>

<template>
  <div>
    <div class="main">
      <h1>Notes</h1>
      <button @click="show" class="vert">+</button>

      <Modal v-if="isShow" :note="addnote" />
    </div>
    <Card :notes="notes" />
  </div>
</template>

<style scoped>
.vert {
  width: 30px;
  height: 30px;
  border-radius: 100%;
  border: 0px;
  background-color: hsla(160, 100%, 37%, 1);
  color: #fff;
  padding: 1, 5rem;
}

.main {
  display: flex;
  justify-content: space-between;
  flex-direction: row;
  align-items: center;
}

.cards-container {
  display: flex;
  flex-wrap: wrap;
}
</style>
