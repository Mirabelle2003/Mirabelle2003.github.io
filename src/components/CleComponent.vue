<template>
    <div>
        <p>L'alias .enter correspond à l'événement de pression de la touche Entrée.</p>
        <input @keyup.enter="submitForm" placeholder="Appuyez sur Entrée" />
      </div>
      <p>L'alias .tab correspond à l'événement de pression de la touche Tab.</p>
      <p>L'alias .delete correspond à l'événement de pression de la touche Supprimer ou Retour arrière.</p>
      <p>L'alias .esc correspond à l'événement de pression de la touche Échap.</p>
      <code-display :initial-code="sampleCodeCle"></code-display>
</template>

<script setup>
import {computed, ref} from 'vue';
import CodeDisplay from './CodedisplayComponent.vue';

function submitForm(){
  console.log("Formulaire soumis avec entrée")
}
const sampleCodeCle = `
<template>
    <div>
        <p>L'alias .enter correspond à l'événement de pression de la touche Entrée.</p>
        <input @keyup.enter="submitForm" placeholder="Appuyez sur Entrée" />
    </div>
    <p>L'alias .tab correspond à l'événement de pression de la touche Tab.</p>
    <p>L'alias .delete correspond à l'événement de pression de la touche Supprimer ou Retour arrière.</p>
    <p>L'alias .esc correspond à l'événement de pression de la touche Échap.</p>
</template>
`;
</script>