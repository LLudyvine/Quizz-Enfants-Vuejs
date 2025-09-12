<script setup lang="ts">
import { ref } from 'vue'
import MathematiqueVuejs from './components/MathematiqueVuejs.vue';
import CultureGVuejs from './components/CultureGVuejs.vue';
import AnglaisVuejs from './components/AnglaisVuejs.vue';
import HistoireVuejs from './components/HistoireVuejs.vue';


const score = ref(0);
</script>

<template>
    <div>
    <h1>Quizz</h1>
    <div class="premiereCategorie">Score : {{ score }}</div>
        <MathematiqueVuejs @incrementScore="() => score++"/>
        <CultureGVuejs @incrementScore="() => score++"/>
        <AnglaisVuejs @incrementScore="() => score++"/>
        <HistoireVuejs @incrementScore="() => score++"/>
    </div>
</template>

<style scoped>
    div {
    background-color : #F0E3A1;
    }
    h1 {
        font-family: cursive;
        font-weight: bold;
        color : #E86146;
        text-align: center;
    }
    .premiereCategorie {
        margin : 10px 370px 0 1000px;
        font-family: cursive;
        font-weight: bold;
        color : #E0AA9F;
        border : dashed #E0AA9F;
        border-width: 3.5px;
        border-radius : 15px;
        height: 30px;
        width: 100px;
        text-align: center;
    }
</style>
