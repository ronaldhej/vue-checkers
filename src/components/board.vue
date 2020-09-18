<template>
<v-container
    fluid
>
  <v-row
      justify="center"
      align="center"
  >
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
        class="justify-center"
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
              v-on:tileClicked="tileClicked"
          />
        </v-col>
      </v-row>
    </v-card>
  </v-row>
  <h1>
    Col: {{selectedTile.col}}, Row: {{selectedTile.row}}, {{selectedTile.currentPiece}}
  </h1>
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
      tileIsPrimed: false,
      snackbar: true,

      selectedTile: {
        row: 1,
        col: 1,
        currentPiece: "none"
      },

      originTile: {
        row: 1,
        col: 1,
        currentPiece: "none"
      },

      destTile: {
        row: 1,
        col: 2,
        currentPiece: "none"
      }
    }

  },

  methods: {
    
    tileClicked: function(row, col, currentPiece) {
      if (this.tileIsPrimed == false) {

        this.originTile.row = row
        this.originTile.col = col
        this.originTile.currentPiece = currentPiece

        this.tileIsPrimed = !(this.tileIsPrimed)

        
      }
    }

  }
}
</script>
