<template>
<v-container
    fluid
>
  <v-row
      justify="center"
      align="center"
  >
    <div
        class="d-md-none text-h3 text-center pl-4 pr-4 font-weight-bold"
    >
      Woah there bud, try use a larger screen to view the checkers board!
    </div>
    <v-snackbar
        v-model="snackbar"
        top
        class="pa-12"
        timeout="4000"
    >
      Now with easy deployment of new builds to the repository! <br/>
      We still have shit checker icons though
      <template v-slot:action="{ attrs }">
        <v-btn
            color="teal"
            text
            v-bind="attrs"
            @click="snackbar = false"
        >
          close
        </v-btn>
      </template>
    </v-snackbar>
    <v-card
        shaped
        elevation="10"
        class="justify-center d-none d-md-block"
        width="850px"
    >
      <v-row
          no-gutters
          justify="center"
          class="pa-6 ma-0 justify-center"
          dense
      >
        <v-col
            v-for="y in 8"
            :key="y"
            cols="auto"
            class="pa-0 ma-0"
        >
          <tile
              v-for="x in 8"
              style="height: 100px; width:100px"
              :key="x"
              :row="x"
              :col="y"
              cols="8"
              sm="1"
              class="pa-0 ma-0"
              outlined
          />
        </v-col>
      </v-row>
    </v-card>
  </v-row>
</v-container>

</template>



<script>
import tile from './tile';

export default {
  name: "board",

  components: {
    tile
  },

  data: function() {
    return {
      snackbar: true
    }

  }
}
</script>
