<script setup>
import { ref } from "vue";
const props = defineProps(['note', 'titre'])

const isClose = ref(true);
const mtitre = ref("");
const mdescription = ref("");

const close = () => {
  isClose.value = !isClose.value;
}; 

</script>

<template>
  <div class="main-modal overlay" v-if="isClose">
    <div class="main">
      <button @click="close">X</button><br>
      <div>
        <label for="name">Titre</label><br />
        <input type="text" id="name" v-model="mtitre" /><br />
        <label for="description">Description</label><br />
        <textarea id="description" v-model="mdescription" cols="30" rows="10"></textarea><br />
        <button @click="note(mtitre, mdescription)" >Ajouter</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.main {
  background-color: rgba(245, 245, 245, 0.83);
  color: #000;
  border-radius: 7px;
  height: 300px;
  width: 400px;
  padding: 3rem;
  display: flex;
  flex-direction: row-reverse;
  justify-content: space-between;
  align-items: baseline;
}

input{
  background-color: rgba(245, 245, 245, 0.83);
  border: transparent;
  width: 250px;
  height: 30px;
  border-radius: 12px;
}

textarea{
  background-color: rgba(245, 245, 245, 0.83);
  border: transparent;
  width: 250px;
  height: 100px;
  border-radius: 12px;
}

.overlay {
  position: absolute;
  background-color: rgba(0, 0, 0, 0.77);
  top: 10%;
  left: 30%;
  z-index: 10;
}
</style>
