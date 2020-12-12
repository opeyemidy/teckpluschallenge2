<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      floating
      app
    >
      <v-list>
        <div style="postion: relative" class="d-flex align-center pl-5">
          <v-avatar color="teal" size="48">
            <span class="white--text headline">lg</span>
          </v-avatar>
          <div class="title pl-2">Application</div>
        </div>
        <v-list-item two-line class="mt-7">
          <v-card color="#f7f8fd" flat width="65%">
            <v-card-text class="d-flex px-2 justify-space-between align-center">
              <div class="mr-2">
                <p class="mb-0 body-1 black--text">Create</p>
                <p class="mb-0 body-1 black--text">New pitch</p>
              </div>
              <v-btn small fab dark color="purple darken-4">
                <v-icon> mdi-plus </v-icon>
              </v-btn>
            </v-card-text>
          </v-card>
        </v-list-item>
        <v-list-item v-for="(item, i) in items" :key="i" exact class="mt-7">
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" fixed flat app color="white">
      <v-app-bar-nav-icon
        class="d-inline-flex d-md-none"
        @click="drawer = !drawer"
      ></v-app-bar-nav-icon>
      <div>
        <v-toolbar-title class="font-weight-medium" v-text="title" />
        <div class="d-none d-sm-block">
          <div class="text-subtitle-2">
            <span class="purple--text text--darken-4">Monday,</span>
            <span class="grey--text">02 March, 2020</span>
          </div>
        </div>
      </div>
      <v-spacer></v-spacer>
      <div class="d-none d-md-block">
        <v-btn icon>
          <v-icon>mdi-email-outline</v-icon>
        </v-btn>
        <v-btn icon>
          <v-icon>mdi-bell-outline</v-icon>
        </v-btn>
        <v-avatar tile color="deep-purple lighten-4">
          <span class="purple--text title text--darken-4">AJ</span>
        </v-avatar>
      </div>
      <v-menu offset-y>
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            :ripple="false"
            v-bind="attrs"
            text
            class="text-capitalize d-inlin-flex d-md-none"
            v-on="on"
            >Alyssa Jones <v-icon>mdi-chevron-down</v-icon></v-btn
          >
        </template>
        <v-list>
          <v-list-item v-for="(item, index) in lists" :key="index">
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>
    <v-main>
      <v-container fluid>
        <nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: true,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Dashboard',
          to: '/',
        },
        {
          icon: 'mdi-square-edit-outline',
          title: 'Editors',
          to: '/inspire',
        },
        {
          icon: 'mdi-account-group-outline',
          title: 'Leads',
          to: '/inspire',
        },
        {
          icon: 'mdi-cog-outline',
          title: 'Settings',
          to: '/inspire',
        },
        {
          icon: 'mdi-file-document-outline',
          title: 'Preview',
          to: '/inspire',
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Dashboard',
      lists: [
        {
          title: 'Notification',
        },
        {
          title: 'Message',
        },
      ],
    }
  },
}
</script>
