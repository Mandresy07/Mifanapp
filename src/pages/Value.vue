<template>
  <div class="q-pa-md">
    <q-infinite-scroll >
      <div class="caption">
        <p>
      Nos valeurs : L'entraide est un moyen de protection pour chaque citoyen, la solidarité est une force pour consolider notre avenir.
        </p>
      </div>
      <template>
        <div class="row justify-center q-my-md">
          <q-spinner-dots color="primary" size="40px" />
        </div>
      </template>
    </q-infinite-scroll>
  </div>
</template>

<script>

import { defineComponent } from 'vue'
export default defineComponent({

  name: 'Value',

})
</script>
