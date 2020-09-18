<template>
  <v-container
      fluid
  >
    <v-app-bar
        color="deep-purple lighten-2"
        class="pa-0 ma-0"
        fixed
        dark
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer">

      </v-app-bar-nav-icon>

      <v-toolbar-title>Ronald's Portfolio Site (Currently work in progress)</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-menu
          left
          bottom
      >
        <template v-slot:activator="{on, attrs}">
          <v-btn
            icon
            v-bind="attrs"
            v-on="on"
            >
              <v-icon>mdi-dots-vertical</v-icon>
          </v-btn>
        </template>

        <v-list>
          <v-list-item
              @click="() => {}"
            >
            <v-list-item-title>English</v-list-item-title>
          </v-list-item>
          <v-list-item
              @click="() => {}"
          >
            <v-list-item-title>Danish</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>


    </v-app-bar>

    <v-navigation-drawer
        v-model="drawer"
        fixed
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
      >
        <v-list-item
            class="pt-2 pb-2"
            @click="() => {}"
        >
          <v-list-item-title
          >
            Homepage
          </v-list-item-title>
        </v-list-item>
        <v-list-item
            class="pt-2 pb-2"
            @click="() => {}"
        >
          <v-list-item-title>Changelog</v-list-item-title>
        </v-list-item>
        <v-list-item
            class="pt-2 pb-2"
            @click="() => {}"
        >
          <v-list-item-title>Checkers</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </v-container>

</template>

<script>
export default {
  name: "appbar",
  data ()
  {
    return {
      drawer: null
    }
  }

}
</script>

<style scoped>

</style>
