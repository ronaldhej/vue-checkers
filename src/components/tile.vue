<template>
  <v-container>
      <v-card
      class="pa-0 ma-0"
      v-once :style="{ 'background-color': colorTiles(row,col), 'background-image': placePieces(row, col)}"
      tile
      height="100px"
      width="100px"
      ripple
      @click="tileClicked(row, col, currentPiece)"
      v-click-outside="onClickOutside"
      >
        <v-img
            height="100px"
            width="100px"
            v-once :src="placePieces(row)"
        >
        </v-img>
      </v-card>
    <v-snackbar
      v-model="snackbar"
    >
      Tile clicked at row: {{row}}, column: {{col}}. The piece is {{currentPiece}}
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
  </v-container>
</template>

<script>
export default
{
  name: "tile",
  props: {
    row: Number,
    col: Number,
    targetTile: Object
  },

  data()
  {
    return {
      // Data goes here
      tileColor: 'white',
      images:
      {
        blackPiece: require('../assets/blackpiece.png'),
        whitePiece: require('../assets/whitepiece.png')
      },
      currentPiece: 'white',
      snackbar: false
    }
  },

  methods: {
    colorTiles: function(row, col)
    {
      if (col % 2 === 0) {
        if(row % 2 === 0) {
          this.tileColor = 'gray'
          return 'gray'
        }
      } else {
        if(row % 2 !== 0) {
          this.tileColor = 'gray'
          return 'gray'
        }        
      }
    },

    placePieces: function (row)
    {
      if (this.tileColor === 'gray')
      {
        switch (row)
        {
          case 1:
            this.currentPiece = 'white'
            return this.images.whitePiece
          case 2:
            this.currentPiece = 'white'
            return this.images.whitePiece
          case 3:
            this.currentPiece = 'white'
            return this.images.whitePiece
          case 6:
            this.currentPiece = 'black'
            return this.images.blackPiece
          case 7:
            this.currentPiece = 'black'
            return this.images.blackPiece
          case 8:
            this.currentPiece = 'black'
            return this.images.blackPiece
          default:
            return this.currentPiece = 'none'
        }
      }
      else
      {
        return this.currentPiece = 'none'
      }
    },
    onClickOutside: function ()
    {
      this.snackbar = false
    },

    tileClicked: function (row, col, currentPiece)
    {
      this.snackbar = true

      this.$emit('tileClicked', row, col, currentPiece)

    }

  }
}
</script>
