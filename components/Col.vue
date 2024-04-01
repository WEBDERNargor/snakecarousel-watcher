<script setup lang="ts">
import { ref } from 'vue';

const items = [
  'https://picsum.photos/600/800?random=1',
  'https://picsum.photos/600/800?random=2',
  'https://picsum.photos/600/800?random=3',
  'https://picsum.photos/600/800?random=4',
  'https://picsum.photos/600/800?random=5',
  'https://picsum.photos/600/800?random=6'
];
const emits=defineEmits(["onGo","onBack"])
const carouselRef:any = ref(null);

const props = defineProps({
  onGo: Function,
  onBack: Function
});





watch(() => props.onGo, (newVal) => {
  if (newVal) {
    carouselRef.value?.next(); 
    emits("onGo")
  }
});

watch(() => props.onBack, (newVal) => {
  if (newVal) {
    carouselRef.value?.prev();
    emits("onBack")
  }
});
</script>

<template>
  <UCarousel ref="carouselRef" :items="items" arrows class="w-64 mx-auto">
    <template #default="{ item }">
      <img :src="item" class="w-full" draggable="false">
    </template>
  </UCarousel>
</template>
