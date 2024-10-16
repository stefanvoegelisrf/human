<template>
    <pre class="mermaid">
        <div id="human-machine-diagram" v-html="humanMachineDiagram"></div>
    </pre>
</template>
<script setup lang="ts">
import mermaid from "mermaid";
const humanMachineDiagramDefinition = `
sequenceDiagram
    box Outer processes
    participant System
    participant Interface
    actor Human
    end
    box Inner processes
    participant Experience
    end
    System->>Interface:Output
    Interface->>Human: Perception
    Human->>Experience: Absorption
    Experience->>Human: Decision
    Human->>Interface: Action
    Interface->>System:Input
`;
onMounted(() => {
    mermaid.initialize({ startOnLoad: false });
    drawDiagram();
});

const humanMachineDiagram = ref<string | null>(null);

const drawDiagram = async () => {
    const { svg } = await mermaid.render("human-machine-diagram-svg", humanMachineDiagramDefinition);
    humanMachineDiagram.value = svg;
}
</script>