<script setup="">
import { defineProps } from "vue";
import MyIcon from "@/assets/MyIcon";
import NextIcon from "@/assets/NextIcon";
const props = defineProps({
  currentPage: {
    type: Number,
    required: true,
  },
  totalPages: {
    type: Number,
    required: true,
  },
  onChangePage: {
    type: Function,
    required: true,
  },
});
</script>

<template>
  <div class="pagination flex items-center">
    <button>
      <MyIcon />
    </button>
    <button
      v-for="index in props.totalPages"
      :key="index"
      @click="props.onChangePage(index)"
      :class="{ active: index === props.currentPage }"
      class="px-4 py-2 border text-purple-600 border border-purple-200 hover:text-white bg-green-400 rounded hover:bg-purple-600 hover:border-transparent"
    >
      {{ index }}
    </button>
    <button>
      <NextIcon />
    </button>
  </div>
</template>

<style scoped>
.active {
  background-color: aquamarine;
}
</style>
