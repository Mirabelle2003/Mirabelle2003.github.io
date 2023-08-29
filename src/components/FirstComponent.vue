<template>
<h2>Je m'appelle {{ variable.name+" "+variable.prenom}}</h2>
<h3>Age : {{ variable.age }}</h3>

</template>

<script setup>
const variable = defineProps(['name', 'prenom', 'age']);
</script>