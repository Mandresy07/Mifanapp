<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated style="background-color: #026b33;">
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title>
          Bienvenu dans notre application
        </q-toolbar-title>

        <img src="../assets/app.jpg" alt="" style="height:70px; border-radius:100px;" >
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
    >
      <q-list>
        <q-item-label
          header
        >
        </q-item-label>

        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'

const linksList = [
  {
    title: 'Tribunal',
    caption: '',
    icon: 'school',
    link: '#/dashboard'
  },
  {
    title: 'Permis',
    caption: '',
    icon: 'payment',
    link: '#/dashboard'
  },
  {
    title: 'CIN',
    caption: '',
    icon: 'add_card',
    link: '#/dashboard'
  },
  {
    title: 'Copie',
    caption: '',
    icon: 'chat',
    link: '#/dashboard'
  },
  {
    title: 'Comment ça marche?',
    caption: '',
    icon: 'help',
    link: '#/dashboard'
  },

  {
    title: 'A propos de Mifan\'App',
    caption: '',
    icon: 'handshake',
    link: '#/dashboard'
  },
  {
    title: 'Nos Valeurs',
    caption: '',
    icon: 'badge',
    link: '#/value'
  },
  {
    title: 'Nous contacter',
    caption: '',
    icon: 'phone',
    link: '#/dashboard'
  },

  {
    title: 'Localisation',
    caption: '',
    icon: 'room',
    link: '#/map'
  },
  //{
  //  title: 'Twitter',
  //  caption: '@quasarframework',
  //  icon: 'rss_feed',
  //  link: 'https://twitter.quasar.dev'
  //},
  //{
  //  title: 'Facebook',
  //  caption: '@QuasarFramework',
  //  icon: 'public',
  //  link: 'https://facebook.quasar.dev'
  //},
  //{
  //  title: 'Quasar Awesome',
  //  caption: 'Community Quasar projects',
  //  icon: 'favorite',
  //  link: 'https://awesome.quasar.dev'
  //}
]

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
})
</script>
