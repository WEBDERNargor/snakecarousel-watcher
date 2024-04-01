<template>
    <div class="w-screen min-h-screen flex justify-center items-center">
        <div>
            <Col @onGo="triggerGoNext" @onBack="triggerGoBack" :onGo="goNext" :onBack="goBack">
            </Col>
            <Bn @go="triggerGoNext" @back="triggerGoBack"></Bn>
        </div>

    </div>

</template>

<script setup lang="ts">


const goNext: any = ref(false);
const goBack: any = ref(false);

const triggerGoNext = () => {
    goNext.value = !goNext.value; // Toggle to trigger watch
};

const triggerGoBack = () => {
    goBack.value = !goBack.value; // Toggle to trigger watch
};
</script>