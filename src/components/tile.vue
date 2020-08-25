<template>
  <v-container>
      <v-card
      outlined
      class="pa-0 ma-0"
      v-bind:style="{ 'background-color': colorTiles(row,col), 'background-image': placePieces(row, col)}"
      tile
      height="100px"
      width="100px"
      ripple
      >
        <v-img
            height="100px"
            width="100px"
            v-once :src="placePieces(row)"
        >
        </v-img>
      </v-card>
  </v-container>
</template>

<script>
export default
{
  name: "tile",
  props: {
    row: Number,
    col: Number
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
      currentPiece: 'white'
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
      if (this.tileColor == 'gray')
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
        }
      }
    }
  }
}

</script>
