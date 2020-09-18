<template>
  <v-navigation-drawer
    v-model="drawer"
    absolute
    temporary
    >
      <v-list-item>
        <v-list-item-avatar>
          <v-img src="https://avatars0.githubusercontent.com/u/8073007?s=460&u=a9a3b8837e6a354e58013e614facea80f9d6f4e5&v=4"></v-img>
        </v-list-item-avatar>

        <v-list-item-content>
          <v-list-item-title>Ronald Johnson</v-list-item-title>
        </v-list-item-content>
      </v-list-item>

    <v-divider></v-divider>

    <v-list
      dense
    >
      <v-list-item>
        <v-list-item-title>Homepage</v-list-item-title>
      </v-list-item>
      <v-list-item>
        <v-list-item-title>Changelog</v-list-item-title>
      </v-list-item>
      <v-list-item
        @click="checkersClicked"
      >
        <v-list-item-title>Checkers</v-list-item-title>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
export default {
  name: "navigationbar",
  props: {
    drawer: null
  },

  methods: {
    checkersClicked: function() {

    }

  }
}
</script>

<style scoped>

</style>
