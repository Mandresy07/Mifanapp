<template>
  <q-layout class="window-height window-width row justify-center items-center" style="background-color: #026b33;">
    <div class="column">
      <div class="row">
        <h5 class="text-h5 text-white q-my-md">Mifan'App</h5>
      </div>
      <div class="row">
        <q-card square bordered class="q-pa-lg shadow-1">
          <q-card-section>
            <q-form class="q-gutter-md">
              <q-input square filled clearable v-model="email" type="email" label="Email" />
              <q-input square filled clearable v-model="password" type="password" label="Mot de passe" />
            </q-form>
          </q-card-section>
          <q-card-actions class="q-px-md">
            <q-btn unelevated style="background-color: #026b33; color:white;" size="lg" class="full-width" label="Se connecter" @click.native="redirect()"/>
          </q-card-actions>
          <q-card-section class="text-center q-pa-none">
            <p class="text-grey-6"></p>
          </q-card-section>
        </q-card>
      </div>
    </div>
  </q-layout>
</template>

<script>
import {defineComponent} from 'vue'
export default defineComponent({
  name: 'Login',
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods:{
    redirect(){
      window.location.href="#/dashboard"
    }
  }
})
</script>

<style>
.q-card {
  width: 360px;
}
</style>
