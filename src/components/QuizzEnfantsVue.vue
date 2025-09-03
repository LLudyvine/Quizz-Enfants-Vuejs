<script setup lang="ts">
import { ref } from 'vue'

const count = ref(0);
const plus = () => {
    count.value++
};
const moins = () => {
    count.value--
};

const deuxiemecount = ref(0);
const deuxiemeplus = () => {
    deuxiemecount.value++
};
const deuxiememoins = () => {
    deuxiemecount.value--
};

const troisiemecount = ref(0);
const troisiemeplus = () => {
    troisiemecount.value++
};
const troisiememoins = () => {
    troisiemecount.value--
};

const quatriemecount = ref(0);
const quatriemeplus = () => {
    quatriemecount.value++
};
const quatriememoins = () => {
    quatriemecount.value--
};

const reponsecultureg = ref("");
const animaux = ref(["Chat", "Chien", "Poule"]);
const reponsechat = () => {
    reponsecultureg.value = "Chat"
    if (reponsecultureg.value === "Chat") {
        return "Bravo tu as réussi la question!🎉"
    }
};
const autrereponse = () => {
    if (reponsecultureg.value === "Chien" || reponsecultureg.value === "Poule") {
        return "Mauvaise réponse😉"
    }
}

const deuxiemereponsecultureg = ref("");
const deuxiemetableauanimaux = ref(["Papillon", "Abeille", "Moustique"]);
const reponseabeille = () => {
    deuxiemereponsecultureg.value = "Abeille"
    if (deuxiemereponsecultureg.value === "Abeille") {
        return "Bravo tu as réussi la question!🎉"
    }
};
const deuxiemeautrereponse = () => {
    if (deuxiemereponsecultureg.value === "Papillon" || deuxiemereponsecultureg.value === "Moustique") {
        return "Mauvaise réponse😉"
    }
}

</script>

<template>
<h1>Quizz</h1>
    <div class="categories">
    <h2>Mathématiques :</h2>
        <p class="question">Combien font 4 + 5 ?</p>
        <p class="resultat" :style="{color : count > 9 ? '#CC4949' : '#784040'}">Résultat : {{ count }}</p>
        <div v-show="count > 8">Bravo tu as réussi la question!🎉</div>
        <button @click="plus">+</button>
        <button @click="moins">-</button>
        <p class="question">Combien d'étoiles il y a t-il "⭐⭐⭐⭐" ?</p>
        <p class="resultat" :style="{color : deuxiemecount > 4 ? '#CC4949' : '#784040'}">Résultat : {{ deuxiemecount }}</p>
        <div v-show="deuxiemecount > 3">Bravo tu as réussi la question!🎉</div>
        <button @click="deuxiemeplus">+</button>
        <button @click="deuxiememoins">-</button>
        <p class="question">Combien font 12 - 3 ?</p>
        <p class="resultat" :style="{color : troisiemecount > 8 ? '#CC4949' : '#784040'}">Résultat : {{ troisiemecount }}</p>
        <div v-show="troisiemecount > 8">Bravo tu as réussi la question!🎉</div>
        <button @click="troisiemeplus">+</button>
        <button @click="troisiememoins">-</button>
        <p class="question">Combien y a t-il de pommes "🍎🍎🍊🍊🍎🍊" ?</p>
        <p class="resultat" :style="{color : quatriemecount > 2 ? '#CC4949' : '#784040'}">Résultat : {{ quatriemecount }}</p>
        <div v-show="quatriemecount > 2">Bravo tu as réussi la question!🎉</div>
        <button @click="quatriemeplus">+</button>
        <button @click="quatriememoins">-</button>
    </div>
    <div class="categories">
    <h2>Culture générale :</h2>
        <p class="question">Quel animal miaule et ronronne ?</p>
        <p class="resultat" :style="{color : reponsecultureg === animaux[0] ? '#CC4949' : '#784040'}">Résultat : {{ reponsecultureg }}</p>
        <button @click="reponsechat">Chat</button>
        <button @click="autrereponse">Chien</button>
        <button @click="autrereponse">Poule</button>
        <p class="question">Comment s'appelle l'insecte qui butine les fleurs pour faire du miel ?</p>
        <p class="resultat" :style="{color : deuxiemereponsecultureg === deuxiemetableauanimaux[1] ? '#CC4949' : '#784040'}">Résultat : {{ deuxiemereponsecultureg }}</p>
        <button @click="deuxiemeautrereponse">Papillon</button>
        <button @click="reponseabeille">Abeille</button>
        <button @click="deuxiemeautrereponse">Moustique</button>
    </div>
</template>

<style scoped>
    h1 {
        font-family: cursive;
        font-weight: bold;
        color : #E86146;
        text-align: center;
    }
    .categories {
        border : dashed #E0AA9F; 
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
    }
</style>
