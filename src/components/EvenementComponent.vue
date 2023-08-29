<template>
    <div>
        <p>L'événement @click permet de réagir lorsque l'utilisateur clique sur un élément.</p>
        <button @click="Hello">Cliquez ici</button>
        <code-display :initial-code="sampleCodeClick"></code-display>
      </div>
      <div>
        <p>L'événement @input est déclenché lorsqu'une entrée utilisateur change, comme lorsqu'un champ de formulaire est modifié.</p>
        <input type="text" v-model="mes" @input="ModifierInput" />
        <code-display :initial-code="sampleCodeInput"></code-display>
      </div>
      <div>
        <p>Vous pouvez passer des paramètres personnalisés à une méthode d'événement en utilisant $event.</p>
        <button @click="greet('Bonjour')">Cliquez pour saluer</button>
        <code-display :initial-code="sampleCodeEvent"></code-display>
      </div>
      <div>
        <p>Vous pouvez empêcher la propagation de l'événement parent en utilisant la directive .stop.</p>
        <div @click="parentClick">
          <button @click.stop="enfantClick">Cliquez ici</button>
        </div>
        <code-display :initial-code="sampleCodeStop"></code-display>
      </div>
      <div>
        <p>Vous pouvez empêcher le comportement par défaut d'un événement en utilisant la directive .prevent.</p>
        <p>Autres modificateurs d'évènements : .self, .capture, .once, .passive</p>
      </div>
</template>

<script setup>
import {computed, ref} from 'vue';
import CodeDisplay from './CodedisplayComponent.vue';

const message = ref("");
  const isUserLoggedIn = true;
  const username = "Utilisateur";
  const posts = ref([
    { id: 1, title: 'La vie est belle' },
    { id: 2, title: 'Le monde est beau' },
    { id: 3, title: 'Le ciel est bleu' }
  ])
  function Hello(){
    alert("Bonjour !");
  }
  
  const showMessage = true;
  const mes = ref("")
  
      function ModifierInput() {
        alert("Entrée modifiée ");
      }
  function greet(greeting){
    alert(greeting +' depuis l\'ASIN')
  }
  function parentClick(){
    alert('Le clic du parent')
  }
  function enfantClick(){
    alert('Le clic de l\'enfant')
  }
  const sampleCodeClick = `
<template>
    <p>L'événement @click permet de réagir lorsque l'utilisateur clique sur un élément.</p>
    <button @click="Hello">Cliquez ici</button>
</template>
  `;
  const sampleCodeInput = `
<template>
    <p>L'événement @input est déclenché lorsqu'une entrée utilisateur change, comme lorsqu'un champ de formulaire est modifié.</p>
    <input type="text" v-model="mes" @input="ModifierInput" />
</template>
  `;
  const sampleCodeEvent = `
<template>
    <p>Vous pouvez passer des paramètres personnalisés à une méthode d'événement en utilisant $event.</p>
    <button @click="greet('Bonjour')">Cliquez pour saluer</button>
</template>
  `;
  const sampleCodeStop = `
<template>
    <p>Vous pouvez empêcher la propagation de l'événement parent en utilisant la directive .stop.</p>
    <div @click="parentClick">
      <button @click.stop="enfantClick">Cliquez ici</button>
    </div>
</template>
  `;
</script>