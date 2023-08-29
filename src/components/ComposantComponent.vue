<template>
 <div>
    <PointComponent titre="Les composants"></PointComponent>
    <p>Les composants permettent de diviser l'interface utilisateur en éléments indépendants et reutilisable</p>
    <code-display :initial-code="sampleCode"></code-display>
</div>
</template>
    
<script setup>
    import CodeDisplay from './CodedisplayComponent.vue';
    const titre = defineProps(['titre']);
    const sampleCode = `
<template>
    <div>
       <PointComponent titre="Les composants"></PointComponent>
       <p>Les composants permettent de diviser l'interface utilisateur en éléments indépendants et reutilisable</p>
       <code-display :initial-code="sampleCode" />
    </div>
</template>
    `;
 

</script>
    
<style></style>
