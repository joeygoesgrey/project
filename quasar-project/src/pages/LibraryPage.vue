<template>
    <q-page class="q-mt-md  sm:p-5 p-3">
        <h5 class="font-bold q-mt-sm q-mb-sm text-center"> 9 Books </h5>
        <div class="grid md:grid-cols-4 grid-cols-2 gap-2">
            <q-card flat class="col-md-4 col-12" v-for="i in 15" :key="i">
                <div class="relative">
                    <img src="https://cdn.dribbble.com/userupload/10908137/file/original-04181f2282e8f937e82cdd940846d41c.jpg?resize=1024x647"
                        class="card-image rounded-xl" loading="lazy">
                    <q-card-section>
                        <div class="inline-flex ">
                            <q-knob :min="0" :max="10" v-model="value1" show-value size="25px" :thickness="0.33"
                                color="green" track-color="grey-3" class="" /> <span
                                class="text-black text-start my-auto font-bold  ml-2">
                                Kenshaw's pencil of justice
                            </span>
                        </div>
                    </q-card-section>
                </div>
            </q-card>
        </div>

    </q-page>
</template>
  
<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
    data(): { value1: number } { // TypeScript type annotation for the data object
        return {
            value1: 2 // Initialize value1 as a number with initial value 0
        }
    }
});
</script>
  
   