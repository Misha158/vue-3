<script setup>
import { reactive } from "vue";

const mockData = [
  { id: 1, name: "Иван", age: 30, email: "ivan@example.com" },
  { id: 2, name: "Мария", age: 28, email: "maria@example.com" },
  { id: 3, name: "Алексей", age: 35, email: "alex@example.com" },
  { id: 4, name: "Елена", age: 32, email: "elena@example.com" },
  { id: 5, name: "Петр", age: 29, email: "petr@example.com" },
  { id: 6, name: "Анна", age: 31, email: "anna@example.com" },
  { id: 7, name: "Сергей", age: 33, email: "sergey@example.com" },
  { id: 8, name: "Ольга", age: 27, email: "olga@example.com" },
  { id: 9, name: "Дмитрий", age: 34, email: "dmitry@example.com" },
  { id: 10, name: "Татьяна", age: 26, email: "tatiana@example.com" },
];

const data = reactive(mockData);
</script>

<template>
  <div>
    <MyTable :data="data" />
  </div>
</template>

<style scoped></style>
<script>
import MyTable from "@/components/MyTable";
export default {
  components: { MyTable },
};
</script>
