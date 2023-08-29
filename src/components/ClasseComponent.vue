<template>
    <div 
      class="bold"
      :class="[age > 0 ? 'text-blue' : 'text-red']">
        <FirstComponent :name="name" :prenom="prenom" :age="age"></FirstComponent>
    </div>
    <input type="text" v-model="name">
    <input type="text" v-model="prenom">
    <input type="text" v-model="age">
    <code-display :initial-code="sampleCodeClass"></code-display>
</template>

<script setup>
  import {computed, ref} from 'vue';
  import CodeDisplay from './CodedisplayComponent.vue';
  import FirstComponent from './FirstComponent.vue';

  const name = ref('');
  const prenom = ref('');
  const age = ref();
  const sampleCodeClass = `
<template>
    <div 
      class="bold"
      :class="[age > 0 ? 'text-blue' : 'text-red']">
        <FirstComponent :name="name" :prenom="prenom" :age="age"></FirstComponent>
    </div>
    <input type="text" v-model="name">
    <input type="text" v-model="prenom">
    <input type="text" v-model="age">
</template>
`;
</script>

<style>

  .text-red{
    color: red;
  }
  .text-blue{
    color: blue;
  }
</style>
