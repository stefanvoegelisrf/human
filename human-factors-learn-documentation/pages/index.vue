<template>
    <div class="min-h-screen">
        <div class="flex gap-4 items-center">
            <img src="/images/Cover_BW.svg" alt="a face made of multiple ui elements" class="max-h-16" />
            <div class="text-4xl">Human factors in digital design</div>
        </div>
        <div>
            <p>Human factors in digital design focuses on improving the human-machine interaction, with a focus on the
                human.</p>
            <p>This touches various topics, like psychology, social influences, physiology, cognitive capabilities and
                many more.</p>
            <p>To get a better human-machine interaction, it is key to view this as a holistic approach which is
                interdisciplinary.</p>
            <p>At the center, are the users needs, desires and requirements.</p>
        </div>
        <HumanMachineInteraction></HumanMachineInteraction>
        <div class="flex flex-col columns-3">
            <Card v-for="section in sections" :key="section.title" :title="section.title"
                :description="section.description" :image-url="section.imageUrl" :image-alt="section.imageAlt"
                :route="section.route">
            </Card>
        </div>
    </div>
</template>
<script setup lang="ts">
import * as sectionsData from "assets/data/sections.json";
const sections = ref(sectionsData.sections);
</script>