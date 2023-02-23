<script setup>
  import Card from './components/Card.vue'
  import Modal from './components/Modal.vue'

</script>

<template>
  <div>
    <h1>Notes</h1>
    <button class="vert">+</button>
  </div>
</template>

<style scoped>

  .vert{
    width: 30px;
    height: 30px;
    border-radius: 100%;
    border: 0px;
    background-color: hsla(160, 100%, 37%, 1);
    color: #fff;
    /* font-size: 1. ; */
    padding: 1,5rem;
  }

  div{
    display: flex;
    justify-content: space-between;
    flex-direction: row;
    align-items: center;
  }

</style>