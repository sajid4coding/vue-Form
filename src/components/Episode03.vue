<script setup>

    import { ref, reactive } from 'vue'
    const displayImage = ref(true)

</script>
<template>
    <section class="mx-auto container">
        
        <div class="card">
            <div class="card-body">
                <h6 class="text-center">Episode 03</h6>

                <div class="row">
                    <div class="col-sm-6">
                        <p class="text-center bg-primary text-white">Image Access</p>
                        <p class="mb-10" v-if="true==displayImage ? display='on' : display='off'">Image is {{ display }}</p>
                        <label>Display Random Image</label>
                        <input type="checkbox" v-model="displayImage"/>
                    </div>
                    <div class="col-sm-6">
                        <p class="text-center bg-primary text-white">Image</p>
                        <!-- <img v-show="displayImage" class="mt-10 mx-auto w-25" :src="`https://source.unsplash.com/random`" alt="" /> -->
                        
                        <img
                        v-if="displayImage"
                        class="mt-10 mx-auto w-25"
                        :src="`https://source.unsplash.com/random?version=${Math.random()}`"
                        alt=""  />
                    </div>
                </div>
                
            </div>
        </div>

    </section>
</template>