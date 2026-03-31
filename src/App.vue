<template>
    <button @click="throwdice()">Gooi de dobbelstenen</button>
    <br />
    <ul>
        <li v-for="(diceTotal, index) in dice" :key="index">{{ index }} : {{ diceTotal }}</li>
    </ul>
</template>
<script setup>
import {reactive} from 'vue';
const dice = reactive({
    1: 0,
    2: 0,
    3: 0,
    4: 0,
    5: 0,
    6: 0,
});
    
    function resetDice() {
    Object.assign(dice, {1: 0, 2: 0, 3: 0, 4: 0, 5: 0, 6: 0});
}

const throwdice = () => {
        resetDice();
    for (let i = 0; i < 8; i++) {
        let randomNumber = Math.floor(Math.random() * 6 + 1);
        dice[randomNumber] += 1;
    }
    console.log(dice);
};
</script>

<style scoped></style>
