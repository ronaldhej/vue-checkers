<template>
  <v-container>
      <v-card
      outlined
      class="pa-0 ma-0"
      v-bind:style="{ 'background-color': colorTiles(row,col)}"
      tile
      height="100px"
      width="100px"
      ripple
      >
      row:{{row}}, column:{{col}} 
      </v-card>
  </v-container>
</template>

<script>
export default {
  name: "tile",
  props: {
    row: Number,
    col: Number
  },

  data() {
    return {
      tileColor: 'yellow'
    }
  },

  methods: {
    colorTiles: function(row, col) {
      if (col % 2 === 0) {
        if(row % 2 === 0) {
          return 'gray'
        }
      } else {
        if(row % 2 !== 0) {
          return 'gray'
        }        
      }
    }
  }
}

</script>

<style>

</style>
