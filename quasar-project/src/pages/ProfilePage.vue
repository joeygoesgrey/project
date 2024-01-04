<template>
    <q-page class="my-auto  w-full">

        <div class="q-pa-md" style="max-width: 100vw">
            <q-list padding>

                <q-item-label header>Profile management</q-item-label>

                <q-item>
                    <q-item-section avatar>
                        <q-icon color="primary" icon="" />
                    </q-item-section>
                    <q-item-section>List item</q-item-section>
                    <q-item-section side>
                        <q-item-label caption>meta</q-item-label>
                    </q-item-section>
                </q-item>


                <q-separator spaced />

            </q-list>
        </div>
    </q-page>
</template>
  
 
<script>
import { ref, defineComponent } from 'vue'

const menuList = [
    {
        icon: 'inbox',
        label: 'Inbox',
        separator: true
    },
    {
        icon: 'send',
        label: 'Outbox',
        separator: false
    },
    {
        icon: 'delete',
        label: 'Trash',
        separator: false
    },
    {
        icon: 'error',
        label: 'Spam',
        separator: true
    },
    {
        icon: 'settings',
        label: 'Settings',
        separator: false
    },
    {
        icon: 'feedback',
        label: 'Send Feedback',
        separator: false
    },
    {
        icon: 'help',
        iconColor: 'primary',
        label: 'Help',
        separator: false
    }
]

export default defineComponent({
    setup() {
        return {
            drawer: ref(false),
            menuList
        }
    }
})

</script>