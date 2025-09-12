<script setup lang="ts">
import { ref } from 'vue'

const emit = defineEmits(["incrementScore"]);
const premiereReponseHistoire = ref("");
const premierTableauHistoire = ref(["Jaune","Blanc", "Multicolor"]);
const reponseBlanc = () => {
   premiereReponseHistoire.value = "Blanc";
    emit("incrementScore");
};
const reponseJaune = () => {
   premiereReponseHistoire.value = "Jaune";
};

const reponseMulticolor = () => {
   premiereReponseHistoire.value = "Multicolor";
};

const deuxiemeReponseHistoire = ref("");
const deuxiemeTableauHistoire = ref(["La prise de la Bastille","La fin de la première guerre mondiale", "La naissance de Jésus"]);
const reponsePaix = () => {
   deuxiemeReponseHistoire.value = "La fin de la première guerre mondiale";
    emit("incrementScore");
};
const reponseBastille = () => {
   deuxiemeReponseHistoire.value = "La prise de la Bastille";
};

const reponseJesus = () => {
  deuxiemeReponseHistoire.value = "La naissance de Jésus";
};

const troisiemeReponseHistoire = ref("");
const troisiemeTableauHistoire = ref(["Les Germains","Les Gaulois", "Les Slaves de l'Est"]);
const reponseGaulois = () => {
   troisiemeReponseHistoire.value = "Les Gaulois";
    emit("incrementScore");
};
const reponseGermains = () => {
   troisiemeReponseHistoire.value = "Les Germains";
};

const reponseEst = () => {
  troisiemeReponseHistoire.value = "Les Slaves de l'Est";
};

const quatriemeReponseHistoire = ref("");
const quatriemeTableauHistoire = ref(["Noir, Rouge, Jaune","Bleu, Blanc, Rouge", "Vert, Blanc, Rouge"]);
const reponseBleu = () => {
   quatriemeReponseHistoire.value = "Bleu, Blanc, Rouge";
    emit("incrementScore");
};
const reponseNoir = () => {
   quatriemeReponseHistoire.value = "Noir, Rouge, Jaune";
};

const reponseVert = () => {
  quatriemeReponseHistoire.value = "Vert, Blanc, Rouge";
};

</script>

<template>
    <QuizzEnfantsVue/>
     <div class="categories">
        <h2>Histoire :</h2>
        <p class="question">De quel couleur était le cheval blanc d'Henri IV ?</p>
        <p class="resultat" :style="{color : premiereReponseHistoire === premierTableauHistoire[1] ? '#CC4949' : '#784040'}">Résultat : {{ premiereReponseHistoire }}</p>
        <div v-show="premiereReponseHistoire === premierTableauHistoire[1]">Bravo tu as réussi la question!🎉</div>
        <div v-show="premiereReponseHistoire === premierTableauHistoire[0] || premiereReponseHistoire === premierTableauHistoire[2]">Mauvaise réponse😉</div>
        <button @click="reponseJaune">Jaune</button>
        <button @click="reponseBlanc">Blanc</button>
        <button @click="reponseMulticolor">Multicolor</button>

        <p class="question">Que célèbre-t-on le 11 Novembre ?</p>
        <p class="resultat" :style="{color : deuxiemeReponseHistoire === deuxiemeTableauHistoire[1] ? '#CC4949' : '#784040'}">Résultat : {{ deuxiemeReponseHistoire }}</p>
        <div v-show="deuxiemeReponseHistoire === deuxiemeTableauHistoire[1]">Bravo tu as réussi la question!🎉</div>
        <div v-show="deuxiemeReponseHistoire === deuxiemeTableauHistoire[0] || deuxiemeReponseHistoire === deuxiemeTableauHistoire[2]">Mauvaise réponse😉</div>
        <button @click="reponseBastille">La prise de la Bastille</button>
        <button @click="reponsePaix">La fin de la première guerre mondiale</button>
        <button @click="reponseJesus">La naissance de Jésus</button>

        <p class="question">Comment s'appelle la population de la Gaule ?</p>
        <p class="resultat" :style="{color : troisiemeReponseHistoire === troisiemeTableauHistoire[1] ? '#CC4949' : '#784040'}">Résultat : {{ troisiemeReponseHistoire }}</p>
        <div v-show="troisiemeReponseHistoire === troisiemeTableauHistoire[1]">Bravo tu as réussi la question!🎉</div>
        <div v-show="troisiemeReponseHistoire === troisiemeTableauHistoire[0] || troisiemeReponseHistoire === troisiemeTableauHistoire[2]">Mauvaise réponse😉</div>
        <button @click="reponseGaulois">Les Gaulois</button>
        <button @click="reponseGermains">Les Germains</button>
        <button @click="reponseEst">Les Slaves de l'Est</button>

        <p class="question">Quelles sont les couleurs du drapeau ?</p>
        <p class="resultat" :style="{color : quatriemeReponseHistoire === quatriemeTableauHistoire[1] ? '#CC4949' : '#784040'}">Résultat : {{ quatriemeReponseHistoire }}</p>
        <div v-show="quatriemeReponseHistoire === quatriemeTableauHistoire[1]">Bravo tu as réussi la question!🎉</div>
        <div v-show="quatriemeReponseHistoire === quatriemeTableauHistoire[0] || quatriemeReponseHistoire === quatriemeTableauHistoire[2]">Mauvaise réponse😉</div>
        <button @click="reponseNoir">Noir, Rouge, Jaune</button>
        <button @click="reponseVert">Vert, Blanc, Rouge</button>
        <button @click="reponseBleu">Bleu, Blanc, Rouge</button>
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