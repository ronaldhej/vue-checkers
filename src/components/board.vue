<template>
<v-container
    fluid
    class="d-none">
  <v-row
      justify="center"
      align="center"
  >
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
    }

  }
}
</script>
