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
              :ref="'tile' + y + x"
              :key="x"
              :row="x"
              :col="y"
              :targetTile="targetTile"
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
      Origin: col:{{originTile.col}}, row:{{originTile.row}} - {{tileIsPrimed}} -- {{currentRef}} Selected: Col: {{targetTile.col}}, Row: {{targetTile.row}}, {{targetTile.currentPiece}}
  </h1>
  <h2>
    {{refName}}
  </h2>
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

      targetTile: {
        row: 1,
        col: 1,
        originPiece: "none"
      },

      originTile: {
        row: 1,
        col: 1,
        currentPiece: "none"
      },

      currentRef: "null",
      refName: "tile" + 1 + 1
    }

  },

  methods: {
    
    tileClicked: function(row, col, currentPiece) {

      if (this.tileIsPrimed == false) {

        this.originTile.row = row
        this.originTile.col = col
        this.originTile.currentPiece = currentPiece

        this.tileIsPrimed = !(this.tileIsPrimed)

        this.refName = "tile" + col + row
        console.log(this.$refs[this.refName])

      } else {
        
        this.targetTile.row = row
        this.targetTile.col = col
        this.targetTile.originPiece = this.originTile.currentPiece

        this.tileIsPrimed = !(this.tileIsPrimed)


        this.refName = "tile" + col + row
        console.log(this.$refs[this.refName])
        console.log("New selection should be: " + this.targetTile.row + " " + this.targetTile.col)

      }
    }

  }
}
</script>
