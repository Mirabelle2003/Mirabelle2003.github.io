<template>
    <h1 class="entete">QUELQUES NOTIONS SUR VUEJS</h1>
   <div>
    <PointComponent titre="Vue JS"></PointComponent>
    <p>VueJS est un framework JavaScript progressif utilisé pour créer des interfaces utilisateur interactives. </p>
   </div>
   <div>
    <PointComponent titre="Les composants"></PointComponent>
    <ComposantComponent></ComposantComponent>
   </div>
    <div>
      <PointComponent titre="Les directives Vue"></PointComponent>
      <DirectiveComponent></DirectiveComponent>
    </div>
    <div>
      <PointComponent titre="Les évènements"></PointComponent>
      <EvenementComponent></EvenementComponent>
    </div>
    <div>
      <PointComponent titre="Alias de clé"></PointComponent>
      <CleComponent></CleComponent>
    </div>
    <div>
      <PointComponent titre="Les propriétés calculées"></PointComponent>
      <ProprietesComponent></ProprietesComponent>
    </div>
    <div>
      <PointComponent titre="Style"></PointComponent>
      <StyleComponent></StyleComponent>
    </div>
    <div>
      <PointComponent titre="Ajout dynamique d'une classe à un élément avec condition imbriquée"></PointComponent>
      <ClasseComponent></ClasseComponent>
    </div>
    <div>
      <PointComponent titre="Les routages"></PointComponent>
      <RoutageComponent></RoutageComponent>
    </div>
  </template>
  
  
  <script setup>
  import {computed, ref} from 'vue';
  import CodeDisplay from './CodedisplayComponent.vue';  
  import PointComponent from './PointComponent.vue';
  import ComposantComponent from './ComposantComponent.vue';
  import DirectiveComponent from './DirectiveComponent.vue';
  import EvenementComponent from './EvenementComponent.vue';
  import CleComponent from './CleComponent.vue';
  import ProprietesComponent from './ProprietesComponent.vue';
  import StyleComponent from './StyleComponent.vue';
  import ClasseComponent from './ClasseComponent.vue';
  import RoutageComponent from './RoutageComponent.vue';
  </script>
  
  <style scoped>
  .entete{
    color: brown;
    font-weight: bold;
  }
  </style>
  