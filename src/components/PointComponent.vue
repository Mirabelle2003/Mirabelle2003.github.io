<template>
<ul>
    <li>
        <h2>{{ titre .titre}}</h2>
    </li>
</ul>
</template>

<script setup>
const titre = defineProps(['titre']);

</script>

<style></style>