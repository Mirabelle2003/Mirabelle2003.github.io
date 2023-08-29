<template>
    <p>Dans Vue.js, vous pouvez utiliser la directive v-bind pour appliquer des styles CSS dynamiques à des éléments HTML en fonction de données de votre composant.</p>
    <div class="stylestatique">
        <h3>Styles statiques</h3>
        <p>Ceci est un style satatique appliqué grâce aux classes directement dans le style.</p>
        <code-display :initial-code="sampleCodeStatique"></code-display>
        <p>CSS</p>
        <code-display :initial-code="sampleCodeStyle"></code-display>
    </div>
    <div :style="{ color: isActive ? 'green' : 'brown' }">
        <h3>Styles conditionnels</h3>
        <input type="checkbox" v-model="isActive" @click="clickcheckbox">
        <label for="checkbox">{{ isActive }}</label>
        <p>Ceci est un style appliqué avec condition imbriquée</p>
        <code-display :initial-code="sampleCodeConditionnel"></code-display>
    </div>
    <div :style="paragraphStyles">
        <h3>Styles dynamiques</h3>
        <p>Ceci est un paragraphe avec des styles dynamiques et :style et proprieté calculée.</p>
    </div>
    <code-display :initial-code="sampleCodeDynamique"></code-display>
</template>

<script setup>
  import {computed, ref} from 'vue';
  import CodeDisplay from './CodedisplayComponent.vue';

  const num1 = ref(47);
  const num2 = ref(874);
  const sum = computed(()=> {return num1.value*num2.value})
  const paragraphStyles = computed(()=> {return {color : 'blue', fontSize : '14px'}})
  const isActive = ref(true);
  function clickcheckbox(){
    isActive=!isActive
  }
  const sampleCodeStatique= `
<template>
    <div class="stylestatique">
        <h3>Styles statiques</h3>
        <p>Ceci est un style satatique appliqué grâce aux classes directement dans le style.</p>
    </div>
</template>
`;
const sampleCodeStyle = `
<style>
.stylestatique{
    color: purple;
    font-weight: bold;
    font-size: large;
  }
 
</style>
    `;
const sampleCodeConditionnel = `
<template>
    <div :style="{ color: isActive ? 'green' : 'brown' }">
        <h3>Styles conditionnels</h3>
        <input type="checkbox" v-model="isActive" @click="clickcheckbox">
        <label for="checkbox">{{ isActive }}</label>
        <p>Ceci est un style appliqué avec condition imbriquée</p>
    </div>
</template>
`;
const sampleCodeDynamique = `
<template>
    <div :style="paragraphStyles">
        <h3>Styles dynamiques</h3>
        <p>Ceci est un paragraphe avec des styles dynamiques et :style et proprieté calculée.</p>
    </div>
</template>
`;

  </script>

<style>
.stylestatique{
    color: purple;
    font-weight: bold;
    font-size: large;
  }
 
</style>