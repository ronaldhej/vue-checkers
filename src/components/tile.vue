<template>
  <v-container>
      <v-card
      class="pa-0 ma-0"
      :style="{ 'background-color': tileColor, 'background-image': 'url(' + currentPiece + ')'}"
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
        whitePiece: require('../assets/whitepiece.png'),
        noPiece: require('../assets/nopiece.png')
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
        }
      } else {
        if(row % 2 !== 0) {
          this.tileColor = 'gray'
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
            this.currentPiece = this.images.whitePiece
            return this.images.whitePiece
          case 2:
            this.currentPiece = this.images.whitePiece
            return this.images.whitePiece
          case 3:
            this.currentPiece = this.images.whitePiece
            return this.images.whitePiece
          case 6:
            this.currentPiece = this.images.blackPiece
            return this.images.blackPiece
          case 7:
            this.currentPiece = this.images.blackPiece
            return this.images.blackPiece
          case 8:
            this.currentPiece = this.images.blackPiece
            return this.images.blackPiece
          default:
            this.currentPiece = this.images.noPiece
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
      this.currentPiece = this.images.noPiece

      console.log(this.targetTile.col + " " + this.targetTile.row)

      if(col == this.targetTile.col && row == this.targetTile.row) {
        console.log("Same")
        this.tileColor = "red"
        if (this.targetTile.originPiece == this.images.whitePiece) {
          console.log("Placing white")
          this.currentPiece = this.images.whitePiece
        } else {
          console.log("Placing black")
          this.currentPiece = this.images.blackPiece
        }
      }

    }

  },

  created() {
    this.colorTiles(this.row, this.col)
    this.placePieces(this.row, this.col)
  }
}
</script>
