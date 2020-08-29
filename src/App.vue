<template>
  <v-app>
    <v-main>
      <appbar/>
      <v-row>
        <homepage/>
        <board
            class="pt-16"
        />
      </v-row>
    </v-main>
  </v-app>
</template>

<script>
import board from './components/board';
import appbar from './components/appbar'
import homepage from "@/components/homepage";

export default {
  name: 'App',

  components: {
    board,
    appbar,
    homepage
  },

  data: () => ({
    //
  }),
};
</script>
