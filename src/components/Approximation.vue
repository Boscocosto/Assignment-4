<script setup>
import { ref } from "vue";

const n2 = ref(0);
const result2 = ref(0);

function Approximation() {
    let piapprox = 0;

    for (let i = 0; i <= n2.value; i++) {
        piapprox += 4 * (Math.pow(-1, i)) / ((2 * i) + 1);
    }

    result2.value = piapprox;
}
</script>

<template>
    <div class="Approximation">
        <h1>Gregory–Leibniz Pi Approximation:</h1>
        <form @submit.prevent="Approximation()">
            <label>n Value:</label>
            <input v-model="n2" type="number" />
            <label>Pi Approximation (Result):</label>
            <input v-model="result2" type="number" readonly />
            <input type="submit" value="Calculate" />
        </form>
    </div>
</template>

<style scoped>
.Approximation {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    gap: 8px;
    padding: 14px;
    background: white;
    border-radius: 18px;
    box-shadow: 0 2px 15px rgba(0, 0, 0, 0.1);
    width: 18%;
    height: auto;
    box-sizing: border-box;
}

.Approximation h1 {
    font-size: 24px;
    color: #000000;
    margin-bottom: 14px;
    font-family: 'Roboto', sans-serif;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 1px;
}

label {
    font-size: 14px;
    color: #000000;
    margin-top: 8px;
    display: block;
    text-align: left;
    word-wrap: break-word;
}

input[type="number"] {
    width: 100%;
    padding: 10px;
    margin-top: 6px;
    border-radius: 6px;
    border: 1px solid #000000;
    background-color: rgba(255, 255, 255, 0.2);
    color: black;
    font-size: 16px;
    text-align: center;
    outline: none;
    transition: border-color 0.3s ease;
    box-sizing: border-box;
}

input[type="submit"] {
    width: 100%;
    padding: 10px;
    margin-top: 14px;
    background-color: #28a745;
    color: white;
    font-size: 16px;
    border: none;
    border-radius: 6px;
    cursor: pointer;
    transition: transform 0.3s ease, background-color 0.3s ease;
    box-sizing: border-box;
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
    margin-top: 8px;
}
</style>