<template>
  <v-app>
    <v-main>
      <appbar/>
      <board
          class="pt-16 d-md-block"
      />
    </v-main>
  </v-app>
</template>

<script>
import board from './components/board';
import appbar from './components/appbar'

export default {
  name: 'App',

  components: {
    board,
    appbar
  },

  data: () => ({
    //
  }),
};
</script>
