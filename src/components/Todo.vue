<script setup>
import { ref } from "vue";

const tasks = ref([
  { name: "風呂", end: 0 },
  { name: "スプラ", end: 0 },
]);
const newTaskName = ref("");
const newTaskEnd = ref(0);

const addTask = () => {
  tasks.value.push({ name: newTaskName.value, end: newTaskEnd.value });
};
</script>

<template>
  <div>TodoList</div>
  <div v-for="task in tasks" :key="task.name">
    <div class="task">
      <div v-if="task.end == 0" class="name">{{ task.name }}</div>

      <div v-if="task.end == 0">
        <button @click="task.end++">完了した！</button>
      </div>
    </div>
  </div>

  <div class="com">Completed!</div>
  <div v-for="task in tasks" :key="task.name">
    <div class="task">
      <div v-if="task.end == 1" class="name">{{ task.name }}</div>
    </div>
  </div>
  <div>
    <label>名前<input v-model="newTaskName" type="text" /></label>
    <label>未完なら０を入力<input v-model="newTaskEnd" type="text" /></label>
    <button @click="addTask">add</button>
  </div>
</template>

<style>
.com {
  margin-top: 30px;
  font-weight: bold;
  color: red;
}
</style>
