<script setup>

    import { ref } from 'vue';
    const color = ref('None')

    function getStyle(){
        return {
            color : color.value
        }
    }

</script>

<template>
    <div class="container">
        <div class="card my-5">
            <h6 class="text-center my-3">Episode 01</h6>
            <div class="card-body">
                <h1 class="text-center my-3">The color is <span :style="getStyle()">{{ color }}</span></h1>
                <label for="color">Type Color</label>
                <input id="color" class="form-control" type="text" v-model="color">
            </div>
        </div>
    </div>
</template>