<template>
    <p>Pour une logique complexe, elles incluent les données réactives. Pour déclarer une propriété calculée : computed()</p>
    <div>
        <p>Les propriétés calculées sont utiles pour effectuer des calculs complexes basés sur les données existantes.</p>
        <p>Nombre 1 : {{ num1 }}</p>
        <p>Nombre 2 : {{ num2 }}</p>
        <p>Somme : {{sum}}</p>
    </div>
    <code-display :initial-code="sampleCodeProprietes"></code-display>
</template>

<script setup>

import {computed, ref} from 'vue';
import CodeDisplay from './CodedisplayComponent.vue';

const num1 = ref(47);
const num2 = ref(874);
const sum = computed(()=> {return num1.value*num2.value})
const sampleCodeProprietes = `
<template>
    <p>Pour une logique complexe, elles incluent les données réactives. Pour déclarer une propriété calculée : computed()</p>
    <div>
        <p>Les propriétés calculées sont utiles pour effectuer des calculs complexes basés sur les données existantes.</p>
        <p>Nombre 1 : {{ num1 }}</p>
        <p>Nombre 2 : {{ num2 }}</p>
        <p>Somme : {{sum}}</p>
    </div>
</template>
`;
</script>

