<script setup>
import { ref } from "vue";

const m = ref(0);
const n1 = ref(0);
const result = ref(0);

function Asymptote() {
    let Result = "";
    
    if (m.value === n1.value) {

Result = "The asymptote is horizontal";
}

else if (n1.value > m.value) {

Result = "The asymptote is the x-axis";
}

else if (m.value > n1.value) {

if ((m.value - n1.value) === 1){
    Result =" Linear"
}

else if ((m.value - n1.value) === 2){ 
    Result ="Quadratic"
}

else if ((m.value - n1.value) === 3){ 
    Result ="Cubic"
}

else if ((m.value - n1.value) === 4){ 
    Result ="Quartic"
}

else if ((m.value - n1.value) === 5){ 
    Result ="Quintic"
}

else if ((m.value - n1.value) === 6){ 
    Result ="Sextic"
}

else if ((m.value - n1.value) === 7){ 
    Result ="Septic"
}

else if ((m.value - n1.value) === 8){ 
    Result ="Octic"
}

else if ((m.value - n1.value) === 9){ 
    Result ="Nonic"
}

else if ((m.value - n1.value) === 10){ 
    Result ="Decic"
}
}
    result.value = Result;
}
</script>

<template>
    <div class="Asymptote">
        <h1>Cosine Law Calculator</h1>
        <form @submit.prevent="Asymptote()">
            <label>m Value:</label>
            <input v-model="m" type="number" />
            <label>n Value:</label>
            <input v-model="n1" type="number" />
            <label>Asymptote Type (Result):</label>
            <input v-model="result" type="text" readonly />
            <input type="submit" value="Calculate" />
        </form>
    </div>
</template>

<style>
.Asymptote {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    gap: 10px;
    padding: 20px;
    background: white;
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    width: 20%;
    height: auto;
}

.Asymptote h1 {
    font-size: 32px;
    color: #000000;
    margin-bottom: 20px;
    font-family: 'Roboto', sans-serif;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 1px;
}

label {
    font-size: 16px;
    color: #000000;
    margin-top: 10px;
    display: block;
    text-align: left;
}

input[type="number"] {
    width: 100%;
    padding: 12px;
    margin-top: 8px;
    border-radius: 8px;
    border: 2px solid #000000;
    background-color: rgba(255, 255, 255, 0.2);
    color: black;
    font-size: 18px;
    text-align: center;
    outline: none;
    transition: border-color 0.3s ease;
}

input[type="text"] {
    width: 100%;
    padding: 12px;
    margin-top: 8px;
    border-radius: 8px;
    border: 2px solid #000000;
    background-color: rgba(255, 255, 255, 0.2);
    color: black;
    font-size: 18px;
    text-align: center;
    outline: none;
    transition: border-color 0.3s ease;
}

input[type="submit"] {
    width: 100%;
    padding: 12px;
    margin-top: 20px;
    background-color: #28a745;
    color: white;
    font-size: 18px;
    border: none;
    border-radius: 8px;
    cursor: pointer;
    transition: transform 0.3s ease, background-color 0.3s ease;
}

input[type="submit"]:hover {
    background-color: #218838;
    transform: scale(1.05);
}

input[type="submit"]:active {
    transform: scale(1);
}

input[readonly] {
    background-color: rgba(255, 255, 255, 0.3);
    cursor: not-allowed;
}

form {
    margin-top: 20px;
}
</style>