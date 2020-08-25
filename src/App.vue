<template>
  <v-app>
    <v-main
      style="background-color: black"
    >
      <board
          class="pt-16"
      />
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
