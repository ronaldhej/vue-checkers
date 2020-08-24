<template>
  <v-app>
    <v-main>
      <board/>
    </v-main>
  </v-app>
</template>

<script>
import board from './components/board';

export default {
  name: 'App',

  components: {
    board
  },

  data: () => ({
    //
  }),
};
</script>
