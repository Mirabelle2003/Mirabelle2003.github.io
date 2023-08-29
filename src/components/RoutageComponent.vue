<template>
    <p>Les routages en Vue.js sont gérés par le routeur officiel Vue Router. Il faut l'installer puis le configurer.</p>   
    <div id="app">
      <router-link to="/home">Accueil</router-link>
      <br>
      <router-link to="/about">À propos</router-link>
      <router-view></router-view>
    </div>
    <p class="routage">router.js</p>
    <code-display :initial-code="sampleCodeRouter"></code-display>
    <p class="routage">html</p>
    <code-display :initial-code="sampleCodeRoutage"></code-display>
</template>

<script setup>
import {computed, ref} from 'vue';
import CodeDisplay from './CodedisplayComponent.vue';  
const sampleCodeRouter = `
import { createRouter, createWebHistory } from 'vue-router';
import HomeComponent from './components/HomeComponent.vue';
import AboutComponent from './components/AboutComponent.vue';

const routes = [
  { path: '/home', component: HomeComponent },
  { path: '/about', component: AboutComponent },
];

const router = createRouter({
  history: createWebHistory(),
  routes
});

export default router;
`;
const sampleCodeRoutage = `
<template>
    <p>Les routages en Vue.js sont gérés par le routeur officiel Vue Router. Il faut l'installer puis le configurer.</p>   
    <div id="app">
      <router-link to="/home">Accueil</router-link>
      <br>
      <router-link to="/about">À propos</router-link>
      <router-view></router-view>
    </div>
</template>
`;
</script>

<style>
.routage{
    font-weight:bold;
}

</style>