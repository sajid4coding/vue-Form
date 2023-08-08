<script setup>
import { ref, reactive } from 'vue'
const favColors = ref([])


</script>

<template>
    <section class="mx-auto my-5 container">
        <div class="card">
            <div class="card-body">
                <h6 class="text-center">Episode 04</h6>
                <h1 class="mt-5">You selected color is {{ favColors }}</h1>
                
                <span class="mx-2">Your favorite colors</span> <br/>
                <input class="mx-2" type="checkbox" v-model="favColors" value="red">
                <label for="red">Red</label>
                <input class="mx-2" type="checkbox" v-model="favColors" value="green">
                <label for="green">Green</label>
                <input class="mx-2" type="checkbox" v-model="favColors" value="blue">
                <label for="blue">Blue</label>
            </div>
        </div>
    </section>
</template>
<style scoped></style>