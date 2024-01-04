<template>
  <q-page class="q-mt-md grid md:grid-cols-3 grid-cols-1 gap-2">
    <q-card flat class="col-md-4 col-12" v-for="i in 15" :key="i">
      <div class="relative">
        <img
          src="https://cdn.dribbble.com/userupload/10908137/file/original-04181f2282e8f937e82cdd940846d41c.jpg?resize=1024x647"
          class="card-image rounded-xl" loading="lazy">
        <div class="top-left-overlay flex rounded-3xl opacity-75">
          <img
            src="https://cdn.dribbble.com/userupload/10908137/file/original-04181f2282e8f937e82cdd940846d41c.jpg?resize=1024x647"
            class="h-8 w-8 mr-1 rounded-3xl" loading="lazy">
          <span class="my-auto mr-2 font-black">Comedy</span>
        </div>

        <div class="bottom-right-overlay rounded-3xl opactiy-25">
          <div class="inline-flex ">
            <q-knob :min="0" :max="10" v-model="value1" show-value size="25px" :thickness="0.33" color="green"
              track-color="grey-3" class="" /> <span class="text-white my-auto font-bold font-white ml-2">
              Kenshaw's pencil of justice
            </span>
          </div>

        </div>
      </div>

    </q-card>
  </q-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  data(): 
  { value1: number } { // TypeScript type annotation for the data object
    return {
      value1: 2 // Initialize value1 as a number with initial value 0
    }
  }
});
</script>


<style>
.position-relative {
  position: relative;
}


.card-image {
  width: 100%;
  /* Adjust as needed */
  height: auto;
  /* Adjust as needed */
}

.top-left-overlay {
  position: absolute;
  top: 0;
  left: -1;
  background-color: white;
  /* Optional for visibility */
  /* padding: 5px; */
  margin: 5px;
  /* Adjust as needed */
}

span {
  font-family: 'Hind Madurai', sans-serif;
}

.bottom-right-overlay {
  position: absolute;
  bottom: 0;
  right: 0;
  background-color: rgba(150, 150, 164, 0.5);
  /* background-color: rgba(255, 255, 255, 0.5); */
  /* Optional for visibility */
  margin: 5px;
  padding: 5px;
}
</style>