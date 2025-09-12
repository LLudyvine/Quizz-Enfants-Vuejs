<script setup lang="ts">
import { ref } from 'vue'

const emit = defineEmits(["incrementScore"]);
const count = ref(0);
const plus = () => {
    if (count.value === 9) {
        return 
    }
    count.value++
    if (count.value === 9) {
        emit("incrementScore");
    }
};
const moins = () => {
    if (count.value === 9) {
        return 
    }
    count.value--
};

const deuxiemeCount = ref(0);
const deuxiemePlus = () => {
    if (deuxiemeCount.value === 4) {
        return 
    }
    deuxiemeCount.value++
    if (deuxiemeCount.value === 4) {
       emit("incrementScore");
    }
};
const deuxiemeMoins = () => {
    if (deuxiemeCount.value === 4) {
        return 
    }
    deuxiemeCount.value--
};

const troisiemeCount = ref(0);
const troisiemePlus = () => {
    if (troisiemeCount.value === 9) {
        return 
    }
    troisiemeCount.value++
    if (troisiemeCount.value === 9) {
        emit("incrementScore");
    }
};
const troisiemeMoins = () => {
    if (troisiemeCount.value === 9) {
        return 
    }
    troisiemeCount.value--
};

const quatriemeCount = ref(0);
const quatriemePlus = () => {
    if (quatriemeCount.value === 3) {
        return 
    }
    quatriemeCount.value++
    if (quatriemeCount.value === 3) {
       emit("incrementScore");
    }
};
const quatriemeMoins = () => {
    if (quatriemeCount.value === 3) {
        return 
    }
    quatriemeCount.value--
};

</script>

<template>
    <QuizzEnfantsVue/>
    <div class="categories">
    <h2>Mathématiques :</h2>
        <p class="question">Combien font 4 + 5 ?</p>
        <p class="resultat" :style="{color : count > 8 ? '#CC4949' : '#784040'}">Résultat : {{ count }}</p>
        <div v-show="count > 8">Bravo tu as réussi la question!🎉</div>
        <button @click="plus">+</button>
        <button @click="moins">-</button>

        <p class="question">Combien d'étoiles y a-t-il "⭐⭐⭐⭐" ?</p>
        <p class="resultat" :style="{color : deuxiemeCount > 3 ? '#CC4949' : '#784040'}">Résultat : {{ deuxiemeCount }}</p>
        <div v-show="deuxiemeCount > 3">Bravo tu as réussi la question!🎉</div>
        <button @click="deuxiemePlus">+</button>
        <button @click="deuxiemeMoins">-</button>

        <p class="question">Combien font 12 - 3 ?</p>
        <p class="resultat" :style="{color : troisiemeCount > 8 ? '#CC4949' : '#784040'}">Résultat : {{ troisiemeCount }}</p>
        <div v-show="troisiemeCount > 8">Bravo tu as réussi la question!🎉</div>
        <button @click="troisiemePlus">+</button>
        <button @click="troisiemeMoins">-</button>

        <p class="question">Combien y a-t-il de pommes "🍎🍎🍊🍊🍎🍊" ?</p>
        <p class="resultat" :style="{color : quatriemeCount > 2 ? '#CC4949' : '#784040'}">Résultat : {{ quatriemeCount }}</p>
        <div v-show="quatriemeCount > 2">Bravo tu as réussi la question!🎉</div>
        <button @click="quatriemePlus">+</button>
        <button @click="quatriemeMoins">-</button>
    </div>
</template>

<style scoped>
    .categories {
        border : dashed #E0AA9F; 
        border-width: 5px;
        margin : 20px 300px 10px 300px;
        text-align: center;
    }
    h2 {
        font-family: cursive;
        color : #E89484;
    }
    .question {
        font-family: cursive;
    }
    .resultat {
        font-family: cursive;
        font-weight: bold;
    }
    div {
        font-family: cursive;
    }
    button {
        font-family: cursive;
        font-weight: bold;
        border : dashed #E0AA9F;
        border-width: 3.5px;
    }
    button:hover {
        background-color: #E89484;
    }
</style>