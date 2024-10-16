<template>
    <div class="flex flex-col gap-4 bg-violet">
        <img :src="imageUrl" :alt="imageAlt" />
        <h1>{{ title }}</h1>
        <p>{{ description }}</p>
    </div>
</template>
<script setup lang="ts">
const props = defineProps<{
    imageUrl: string,
    imageAlt: string,
    title: string,
    description: string,
}>();
</script>