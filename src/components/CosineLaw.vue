<script setup>
import { ref } from "vue";

const a = ref(0);
const b = ref(0);
const angleC = ref(0);
const sidec = ref(0);
const CRad = ref(0);

function CosineLaw() {
    CRad.value = angleC.value * (Math.PI / 180);
    sidec.value = Math.sqrt(a.value * a.value + b.value * b.value - 2 * a.value * b.value * Math.cos(CRad.value));
}
</script>

<template>
    <div class="cosine">
        <h1>Cosine Law Calculator</h1>
        <form @submit.prevent="CosineLaw()">
            <label>Side A:</label>
            <input v-model="a" type="number" />
            <label>Side B:</label>
            <input v-model="b" type="number" />
            <label>Angle C:</label>
            <input v-model="angleC" type="number" />
            <label>Side C (Result):</label>
            <input v-model="sidec" type="number" readonly />
            <input type="submit" value="Calculate" />
        </form>
    </div>
</template>

<style scoped>
.cosine {
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

.cosine h1 {
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