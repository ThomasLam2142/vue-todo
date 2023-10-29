<template>
  <div>
    <h1>To-Do List</h1>
    <input type="text" v-model="itemContent" />
    <button @click="addItem(itemContent)">Submit</button>
    <ul>
      <li v-for="(detail, index) in details" :key="index">
        {{ detail }}
        <button @click="removeItem(index)">Delete</button>
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const details = ref(['Item 1', 'Item 2', 'Item 3']);
const itemContent = ref('');

const addItem = (itemContent) => {
    details.value.push(itemContent);
    itemContent.value = '';
};

const removeItem = (index) => {
  details.value.splice(index, 1);
};
</script>


<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
