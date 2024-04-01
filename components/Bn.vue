<template>
    <div>
<button @click="backcompoent" class="bg-[blue]">back</button>
<button @click="gocompoent" class="bg-[red]">go</button>

    </div>
</template>

<script setup lang="ts">
const emits = defineEmits(["go","back"]);
const gocompoent=(e:any)=>{
    emits("go",e)
}
const backcompoent=(e:any)=>{
    emits("back",e)
}
</script>

<style scoped>

</style>