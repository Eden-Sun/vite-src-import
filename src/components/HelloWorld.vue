<script setup>
import { computed, ref } from "vue";

const props = defineProps({
  msg: String,
  icon: String,
});

const count = ref(0);

const failSrc = computed(() => {
  return new URL(props.icon, import.meta.url);
});

const fineSrc = computed(() => {
  return new URL("/src/assets/vue.svg", import.meta.url);
});
</script>

<template>
  <h1>{{ msg }} {{ icon }}</h1>
  <img :src="icon" class="logo" alt="Vue logo" />
  <img :src="failSrc" class="logo" alt="Vue logo" />
  <img :src="fineSrc" class="logo" alt="Vue logo" />
</template>

<style scoped>
img {
  height: 30px;
  width: 30px;
}
</style>
