<script setup>
import ClickCounter from "./ClickCounter.vue";
import ItemList from "./ItemList2.vue";
import todolist from "./Todo.vue";

defineProps({
  msg: { type: String, default: "" },
});
</script>

<template>
  <div>
    <h1>{{ msg }}</h1>
    <ClickCounter />
    <ItemList />
    <todolist />
  </div>
</template>

<style scoped>
a {
  color: #42b983;
}
</style>
