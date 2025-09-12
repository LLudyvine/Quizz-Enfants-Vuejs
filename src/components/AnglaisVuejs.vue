<script setup lang="ts">
import { ref } from 'vue'

const emit = defineEmits(["incrementScore"]);
const premiereReponseAnglais = ref("");
const premierTableauAnglais = ref(["Dog","Turtle", "Horse"]);
const reponseTurtle = () => {
    premiereReponseAnglais.value = "Turtle";
    emit("incrementScore");
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
    emit("incrementScore");
};
const reponseAuRevoir = () => {
   deuxiemeReponseAnglais.value = "Au Revoir";
};

const reponseManger = () => {
   deuxiemeReponseAnglais.value = "Manger";
};

const troisiemeReponseAnglais = ref("");
const troisiemeTableauAnglais = ref(["Chat","Ordinateur", "Télévision"]);
const reponseChatt = () => {
    troisiemeReponseAnglais.value = "Chat";
    emit("incrementScore");
};
const reponseOrdi = () => {
   troisiemeReponseAnglais.value = "Ordinateur";
};

const reponseTele = () => {
   troisiemeReponseAnglais.value = "Télévision";
};

const quatriemeReponseAnglais = ref("");
const quatriemeTableauAnglais = ref(["Burger","Pizza", "Bacon"]);
const reponseBurger = () => {
   quatriemeReponseAnglais.value = "Burger";
    emit("incrementScore");
};
const reponsePizza = () => {
   quatriemeReponseAnglais.value = "Pizza";
};

const reponseBacon = () => {
   quatriemeReponseAnglais.value = "Bacon";
};

const scores = ref(0);
const score = () => {
    scores.value++
}
</script>

<template>
    <QuizzEnfantsVue/>
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
        
        <p class="question">Qu'est ce que veut dire "Cat" ?</p>
        <p class="resultat" :style="{color : troisiemeReponseAnglais === troisiemeTableauAnglais[0] ? '#CC4949' : '#784040'}">Résultat : {{ troisiemeReponseAnglais }}</p>
        <div v-show="troisiemeReponseAnglais === troisiemeTableauAnglais[0]">Bravo tu as réussi la question!🎉</div>
        <div v-show="troisiemeReponseAnglais === troisiemeTableauAnglais[1] || troisiemeReponseAnglais === troisiemeTableauAnglais[2]">Mauvaise réponse😉</div>
        <button @click="reponseTele">Télévision</button>
        <button @click="reponseChatt">Chat</button>
        <button @click="reponseOrdi">Ordinateur</button>

        <p class="question">Comment on dit burger en anglais ?</p>
        <p class="resultat" :style="{color : quatriemeReponseAnglais === quatriemeTableauAnglais[0] ? '#CC4949' : '#784040'}">Résultat : {{ quatriemeReponseAnglais }}</p>
        <div v-show="quatriemeReponseAnglais === quatriemeTableauAnglais[0]">Bravo tu as réussi la question!🎉</div>
        <div v-show="quatriemeReponseAnglais === quatriemeTableauAnglais[1] || quatriemeReponseAnglais === quatriemeTableauAnglais[2]">Mauvaise réponse😉</div>
        <button @click="reponseBurger">Burger</button>
        <button @click="reponsePizza">Pizza</button>
        <button @click="reponseBacon">Bacon</button>
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