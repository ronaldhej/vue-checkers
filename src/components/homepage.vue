<template>
  <v-container
    fluid
    >
    <v-parallax
        dark
        height="600"
        src="../assets/ribbongraphic.jpg"
    >
      <v-row
          align="center"
          justify="center"
      >
        <v-col class="text-center" cols="12">
          <h1 class="display-1 font-weight-thin white--text mb-4">Ronald Johnson</h1>
          <h4 class="subheading white--text">Website solutions with a Kiwi accent</h4>
        </v-col>
      </v-row>
    </v-parallax>
    <v-divider
        class="mt-6 mb-6 ml-3 mr-3"
    ></v-divider>
    <v-row
    align="center"
    justify="center"    
    >
    <v-card
    v-for="i in 8"
    :key="i"
    width="600"
    elevation="8"
    class="ma-8"
    >
      <v-card-title>
        This is card number {{i}}        
      </v-card-title>
      <v-card-text>
        Blah blah blah content
      </v-card-text>
      <v-card-actions
      class="justify-end align-end"
      >
        <v-btn
        text
        color="purple"
        >
          Share
        </v-btn>
        <v-btn
        text
        color="purple"
        >
          Open
        </v-btn>
      </v-card-actions>
    </v-card>

    </v-row>
  </v-container>
</template>

<script>
export default {
name: "homepage"
}
</script>

<style scoped>

</style>
