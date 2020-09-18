<template>
  <v-app>
    <v-main>
      <appbar/>
      <v-row>
        <homepage/>
        <!--<board
            class="pt-16 d-none d-md-block"
        />-->
      </v-row>
      <v-row>
        <board/>
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
