<script setup>

import { ref, reactive } from 'vue'
const saarcCountries = reactive([
  { name: "Bangladesh", capital: "Dhaka" },
  { name: "Nepal", capital: "Kathmandu" },
  { name: "Bhutan", capital: "Thimphu" },
  { name: "Sri Lanka", capital: "Colombo" },
  { name: "India", capital: "New Delhi" },
  { name: "Pakistan", capital: "Islamabad" },
  { name: "Maldives", capital: "Male" }
])

const capitals = ["Dhaka", "Kathmandu", "Thimphu", "Colombo", "New Delhi", "Islamabad", "Male"]

function getScore(){
    let score = 0
    saarcCountries.forEach(country => {
        if(country.answer == country.capital){
            score++
        }
    })
    return score
}

const displayScore = ref(false)
function getResult(){
    displayScore.value = true
}


</script>

<template>
    <section class="mx-auto my-5 container">
        <div class="card">
            <div class="card-body">
                <h6 class="text-center">Episode 05</h6>

                <p class="mb-10 text-center">QNA</p>

                <div class="my-2 border border-gray-400 p-3" v-for="country in saarcCountries">
                    <p>What is the capital of {{ country.name }} ?</p>
                    <template v-for="capital in capitals" :key="index">
                        <input type="radio" :value="capital" v-model="country.answer"/>
                        <label class="ml-2 mx-2">{{ capital }}</label>
                    </template>
                </div>
                <div class="d-grid gap-2 col-6 mx-auto my-5">
                    <h2 class="text-center" v-if="true==displayScore">Your Score: {{ getScore() }} out of 7</h2>
                    <button class="btn btn-warning" @click="getResult()">Get Result</button>
                </div>
            </div>
        </div>
    </section>
</template>