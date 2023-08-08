<script setup>

    import { ref, reactive } from 'vue'
    const person = reactive({
        name: 'John Doe',
        age: 30,
        job: 'Web Developer',
    })

</script>

<template>
    <div class="container">
        <div class="card my-5">
            <h6 class="text-center my-3">Episode 02</h6>
            <div class="card-body">
                <h1 class="text-center my-3">All data is <span style="color: #0000009a;">{{ person }}</span></h1>
                <div class="my-3" v-for="(value, key, index) in person" :key="index">
                    <label :for="key" style="text-transform: capitalize;">{{ key }}</label>
                    <input :id="key" class="form-control" type="text" v-model="person[key]">
                </div>
            </div>
        </div>
    </div>
</template>