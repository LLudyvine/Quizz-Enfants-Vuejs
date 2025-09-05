<script setup lang="ts">
import { ref } from 'vue'

const count = ref(0);
const plus = () => {
    if (count.value === 9) {
        return 
    }
    count.value++
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
};
const quatriemeMoins = () => {
    if (quatriemeCount.value === 3) {
        return 
    }
    quatriemeCount.value--
};

const reponseCultureg = ref("");
const animaux = ref(["Chat", "Chien", "Poule"]);
const reponseChat = () => {
    reponseCultureg.value = "Chat";
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
};
const reponseCarotte = () => {
    quatriemeReponseCultureg.value = "Une Carotte";
};

const reponsePommeDeTerre = () => {
   quatriemeReponseCultureg.value = "Une Pomme de terre";
};

const premiereReponseAnglais = ref("");
const premierTableauAnglais = ref(["Dog","Turtle", "Horse"]);
const reponseTurtle = () => {
    premiereReponseAnglais.value = "Turtle";
};
const reponseDog = () => {
    premiereReponseAnglais.value = "Dog";
};

const reponseHorse = () => {
   premiereReponseAnglais.value = "Horse";
};

const deuxiemeReponseAnglais = ref("");
const deuxiemeTableauAnglais = ref(["Manger","Au Revoir", "Bonjour"]);
const reponseBonjour = () => {
    deuxiemeReponseAnglais.value = "Bonjour";
};
const reponseAuRevoir = () => {
   deuxiemeReponseAnglais.value = "Au Revoir";
};

const reponseManger = () => {
   deuxiemeReponseAnglais.value = "Manger";
};

</script>

<template>
<h1>Quizz</h1>
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
    <div class="categories">
        <h2>Anglais :</h2>
        <p class="question">Comment on dit tortue en anglais ?</p>
        <p class="resultat" :style="{color : premiereReponseAnglais === premierTableauAnglais[1] ? '#CC4949' : '#784040'}">Résultat : {{ premiereReponseAnglais }}</p>
        <div v-show="premiereReponseAnglais === premierTableauAnglais[1]">Bravo tu as réussi la question!🎉</div>
        <div v-show="premiereReponseAnglais === premierTableauAnglais[0] || premiereReponseAnglais === premierTableauAnglais[2]">Mauvaise réponse😉</div>
        <button @click="reponseTurtle">Turtle</button>
        <button @click="reponseDog">Dog</button>
        <button @click="reponseHorse">Horse</button>

        <p class="question">Qu'est ce que veut dire "Hello" ?</p>
        <p class="resultat" :style="{color : deuxiemeReponseAnglais === deuxiemeTableauAnglais[2] ? '#CC4949' : '#784040'}">Résultat : {{ deuxiemeReponseAnglais }}</p>
        <div v-show="deuxiemeReponseAnglais === deuxiemeTableauAnglais[2]">Bravo tu as réussi la question!🎉</div>
        <div v-show="deuxiemeReponseAnglais === deuxiemeTableauAnglais[0] || deuxiemeReponseAnglais === deuxiemeTableauAnglais[1]">Mauvaise réponse😉</div>
        <button @click="reponseManger">Manger</button>
        <button @click="reponseAuRevoir">Au Revoir</button>
        <button @click="reponseBonjour">Bonjour</button>
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
