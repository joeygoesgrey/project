<template>
  <q-layout view="hHh Lpr fFf" class="shadow-2 rounded-borders ">
    <q-header class="text-black bg-white" height-hint="8">

      <q-toolbar>
        <div class="w-full">
          <q-toolbar class="bg-white text-black rounded-borders">
            <q-toolbar-title class="title">
              LittleListen
            </q-toolbar-title>

            <q-space />
            <q-input v-model="search" bordered rounded flat dense placeholder="Search" input-class="text-start">
              <template v-slot:append>
                <q-icon name="search" />
              </template>
            </q-input>

          </q-toolbar>
        </div>



        <!-- <q-btn name="notifications" icon="notifications" flat round dense>
          <q-badge color="green" floating class="opacity-50">1</q-badge>
        </q-btn> -->
      </q-toolbar>
      <q-toolbar class="justify-between flex" v-if="currentPath == '/'">
        <div>
          <q-tabs active-color="black" content-class="justify-evenly text-grey-7 font-bold" indicator-color="transparent"
            dense switch-indicator>
            <q-route-tab to="/" label="Explore" no-caps />
            <q-route-tab to="/" label="Audio" no-caps />
            <q-route-tab to="/" label="Read" no-caps />
          </q-tabs>
        </div>
        <q-icon name="menu" color="black" size="24px" @click="show()" />

      </q-toolbar>

    </q-header>

    <q-page-container>
      <router-view />
      <q-page-scroller position="bottom-right" :scroll-offset="150" :offset="[18, 18]">
        <q-btn fab icon="keyboard_arrow_up" class="bg-ise" />
      </q-page-scroller>
    </q-page-container>

    <q-footer reveal class="rounded-2xl bg-white">
      <q-tabs narrow-indicator active-color="green" content-class="justify-evenly" indicator-color="transparent" dense
        switch-indicator>
        <q-route-tab icon="book" class="text-black" to="/library" />

        <q-route-tab icon="home" class="text-black" to="/" />

        <q-route-tab to="/profile" rounded>
          <q-avatar size="24px">
            <img
              src="https://p16-sign-useast2a.tiktokcdn.com/tos-useast2a-avt-0068-euttp/8dc8667345d0ef90e417cfe5931b9115~c5_100x100.jpeg?x-expires=1701680400&x-signature=bE5WcJKWEOb9EfXtHwY2ATF4qWU%3D">
          </q-avatar>
        </q-route-tab>

        <q-route-tab icon="widgets" class="text-black" to="/" />
        <q-route-tab icon="admin_panel_settings" class="text-black" to="/" />

      </q-tabs>

    </q-footer>

  </q-layout>
</template>
 
<script>
import { useQuasar } from 'quasar'
import { defineComponent, } from 'vue';

export default defineComponent({

  setup() {
    const $q = useQuasar()

    function show(grid) {
      $q.bottomSheet({
        message: 'Choose Topic',
        grid,
        actions: [
          {
            label: 'Fables',
            img: 'https://plus.unsplash.com/premium_photo-1683133569392-f85efe0620ef?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MjE3fHxjYXJ0b29ufGVufDB8fDB8fHww',
            id: 'Fables'
          },
          {
            label: 'Early Reader',
            img: 'https://plus.unsplash.com/premium_photo-1683133569392-f85efe0620ef?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MjE3fHxjYXJ0b29ufGVufDB8fDB8fHww',
            id: 'Early Reader'
          },
          {
            label: 'Adventure',
            img: 'https://plus.unsplash.com/premium_photo-1683133569392-f85efe0620ef?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MjE3fHxjYXJ0b29ufGVufDB8fDB8fHww',
            id: 'Adventure'
          },
          {
            label: 'Adventure',
            img: 'https://plus.unsplash.com/premium_photo-1683133569392-f85efe0620ef?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MjE3fHxjYXJ0b29ufGVufDB8fDB8fHww',
            id: 'Adventure'
          },
          {
            label: 'Animals',
            img: 'https://plus.unsplash.com/premium_photo-1683133569392-f85efe0620ef?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MjE3fHxjYXJ0b29ufGVufDB8fDB8fHww',
            id: 'Animals'
          },
          {
            label: 'Bedtime Stories',
            img: 'https://plus.unsplash.com/premium_photo-1683133569392-f85efe0620ef?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MjE3fHxjYXJ0b29ufGVufDB8fDB8fHww',
            id: 'Bedtime Stories'
          }, {
            label: 'Picture Books',
            img: 'https://plus.unsplash.com/premium_photo-1683133569392-f85efe0620ef?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MjE3fHxjYXJ0b29ufGVufDB8fDB8fHww',
            id: 'Picture Books'
          },

        ]
      }).onCancel(() => {
        // console.log('Dismissed')
      }).onDismiss(() => {
        // console.log('I am triggered on both OK and Cancel')
      })
    }

    return { show }
  },
  computed: {
    currentPath() {
      return this.$route.path;
    }
  }
})
</script>