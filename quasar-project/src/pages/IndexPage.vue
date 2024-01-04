<template>
  <q-page class="sm:p-5 p-3">
    <maincomponent />
  </q-page>
</template>

<script lang="ts">
import maincomponent from 'components/MainHome.vue';
import { defineComponent } from 'vue';

export default defineComponent({
  components: { maincomponent },

});
</script>
