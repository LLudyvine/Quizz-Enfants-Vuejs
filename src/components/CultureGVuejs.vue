<script setup lang="ts">
import { ref } from 'vue'

const emit = defineEmits(["incrementScore"]);
const reponseCultureg = ref("");
const animaux = ref(["Chat", "Chien", "Poule"]);
const reponseChat = () => {
    reponseCultureg.value = "Chat";
    emit("incrementScore");
}
const reponseChien = () => {
    reponseCultureg.value = "Chien";
}
const reponsePoule = () => {
    reponseCultureg.value = "Poule";
}


const deuxiemeReponseCultureg = ref("");
const deuxiemeTableauAnimaux = ref(["Papillon", "Abeille", "Moustique"]);
const reponseAbeille = () => {
    deuxiemeReponseCultureg.value = "Abeille";
    emit("incrementScore");
};
const reponseMoustique = () => {
  deuxiemeReponseCultureg.value = "Moustique";
};

const reponsePapillon = () => {
    deuxiemeReponseCultureg.value = "Papillon";
};

const troisiemeReponseCultureg = ref("");
const troisiemeTableauBallon = ref(["Ballon de Foot", "Ballon de Basket", "Ballon de Rugby"]);
const reponseRugby = () => {
    troisiemeReponseCultureg.value = "Ballon de Rugby";
    emit("incrementScore");
};
const reponseFoot = () => {
  troisiemeReponseCultureg.value = "Ballon de Foot";
};

const reponseBasket = () => {
   troisiemeReponseCultureg.value = "Ballon de Basket";
};

const quatriemeReponseCultureg = ref("");
const quatriemeTableauHalloween = ref(["Une Citrouille", "Une Carotte", "Une Pomme de terre"]);
const reponseCitrouille = () => {
    quatriemeReponseCultureg.value = "Une Citrouille";
    emit("incrementScore");
};
const reponseCarotte = () => {
    quatriemeReponseCultureg.value = "Une Carotte";
};

const reponsePommeDeTerre = () => {
   quatriemeReponseCultureg.value = "Une Pomme de terre";
};

const scores = ref(0);
const score = () => {
    scores.value++
}
</script>

<template>
    <QuizzEnfantsVue/>
    <div class="categories">
    <h2>Culture générale :</h2>
        <p class="question">Quel animal miaule et ronronne ?</p>
        <p class="resultat" :style="{color : reponseCultureg === animaux[0] ? '#CC4949' : '#784040'}">Résultat : {{ reponseCultureg }}</p>
        <div v-show="reponseCultureg === animaux[0]">Bravo tu as réussi la question!🎉</div>
        <div v-show="reponseCultureg === animaux[1] || reponseCultureg === animaux[2]">Mauvaise réponse😉</div>
        <button @click="reponseChat">Chat</button>
        <button @click="reponseChien">Chien</button>
        <button @click="reponsePoule">Poule</button>

        <p class="question">Comment s'appelle l'insecte qui butine les fleurs pour faire du miel ?</p>
        <p class="resultat" :style="{color : deuxiemeReponseCultureg === deuxiemeTableauAnimaux[1] ? '#CC4949' : '#784040'}">Résultat : {{ deuxiemeReponseCultureg }}</p>
        <div v-show="deuxiemeReponseCultureg === deuxiemeTableauAnimaux[1]">Bravo tu as réussi la question!🎉</div>
        <div v-show="deuxiemeReponseCultureg === deuxiemeTableauAnimaux[0] || deuxiemeReponseCultureg === deuxiemeTableauAnimaux[2]">Mauvaise réponse😉</div>
        <button @click="reponsePapillon">Papillon</button>
        <button @click="reponseAbeille">Abeille</button>
        <button @click="reponseMoustique">Moustique</button>

        <p class="question">Comment s'appelle ce ballon "🏈" ?</p>
        <p class="resultat" :style="{color : troisiemeReponseCultureg === troisiemeTableauBallon[2] ? '#CC4949' : '#784040'}">Résultat : {{ troisiemeReponseCultureg }}</p>
        <div v-show="troisiemeReponseCultureg === troisiemeTableauBallon[2]">Bravo tu as réussi la question!🎉</div>
        <div v-show="troisiemeReponseCultureg === troisiemeTableauBallon[0] || troisiemeReponseCultureg === troisiemeTableauBallon[1]">Mauvaise réponse😉</div>
        <button @click="reponseFoot">Ballon de Foot</button>
        <button @click="reponseBasket">Ballon de Basket</button>
        <button @click="reponseRugby">Ballon de Rugby</button>

        <p class="question">Quel légume est souvent associé à Halloween ?</p>
        <p class="resultat" :style="{color : quatriemeReponseCultureg === quatriemeTableauHalloween[0] ? '#CC4949' : '#784040'}">Résultat : {{ quatriemeReponseCultureg }}</p>
        <div v-show="quatriemeReponseCultureg === quatriemeTableauHalloween[0]">Bravo tu as réussi la question!🎉</div>
        <div v-show="quatriemeReponseCultureg === quatriemeTableauHalloween[1] || quatriemeReponseCultureg === quatriemeTableauHalloween[2]">Mauvaise réponse😉</div>
        <button @click="reponseCarotte">Une Carotte</button>
        <button @click="reponseCitrouille">Une Citrouille</button>
        <button @click="reponsePommeDeTerre">Une Pomme de terre</button>
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