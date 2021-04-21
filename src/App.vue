<template>
  <v-app>
    <v-card>
      <v-navigation-drawer
        v-model="drawer"
        app
        permanent
        width="150px"
        padding="10px"
      >
        <v-spacer></v-spacer>
        <v-list nav dense>
          <v-list-item link>
            <v-list-item-icon>
              <v-icon>mdi-folder</v-icon>
            </v-list-item-icon>
            <router-link to="/"
              ><v-list-item-title>Home</v-list-item-title></router-link
            >
          </v-list-item>
          <v-list-item link>
            <v-list-item-icon>
              <v-icon>mdi-account-multiple</v-icon>
            </v-list-item-icon>

            <router-link :to="{ name: 'About' }">
              <v-list-item-title>About</v-list-item-title></router-link
            >
          </v-list-item>
        </v-list>
      </v-navigation-drawer>
    </v-card>

    <v-main>
      <router-view />
    </v-main>

    <v-footer dark padless>
      <v-card class="flex" flat tile>
        <v-card-title class="teal">
          <strong class="subheading"
            >Get connected with us on social networks!</strong
          >

          <v-spacer></v-spacer>

          <v-btn v-for="icon in icons" :key="icon" class="mx-4" dark icon>
            <v-icon size="24px">
              {{ icon }}
            </v-icon>
          </v-btn>
        </v-card-title>

        <v-card-text class="py-2 white--text text-center">
          {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
        </v-card-text>
      </v-card>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    //
  }),
};
</script>
