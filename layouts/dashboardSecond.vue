<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      floating
      app
      dark
      color="#232946"
    >
      <v-list>
        <div style="postion: relative" class="d-flex align-center pl-5">
          <v-avatar color="teal" size="48">
            <span class="white--text headline">lg</span>
          </v-avatar>
          <div class="title pl-2">Application</div>
        </div>
        <v-list-item>
          <div class="my-12"></div>
        </v-list-item>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          exact
          class="mt-7 ml-3"
          nuxt
          :to="item.to"
          active-class="red lighten-4 indigo--text text--darken-4 radius-active-class"
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" fixed flat app dark color="#232946">
      <v-app-bar-nav-icon
        class="d-inline-flex d-md-none"
        @click="drawer = !drawer"
      ></v-app-bar-nav-icon>
      <div>
        <v-text-field
          hide-details
          outlined
          dense
          filled
          prepend-inner-icon="mdi-magnify"
          color="black"
        ></v-text-field>
      </div>
      <v-spacer></v-spacer>
      <div class="d-none d-md-inline-flex">
        <div class="mr-12 d-inline-flex">
          <div
            style="position: relative; margin: 0 5px"
            class="d-flex justify-center align-center"
          >
            <div
              style="
                position: absolute;
                height: 30px;
                width: 30px;
                opacity: 0.3;
                border-radius: 5px;
              "
              class="white"
            ></div>
            <v-btn icon small>
              <v-icon>mdi-message-outline</v-icon>
            </v-btn>
          </div>
          <div
            style="position: relative; margin: 0 5px"
            class="d-flex justify-center align-center"
          >
            <div
              style="
                position: absolute;
                height: 30px;
                width: 30px;
                opacity: 0.3;
                border-radius: 5px;
              "
              class="white"
            ></div>

            <v-btn icon small>
              <v-badge color="#f2c94c" overlap dot>
                <v-icon>mdi-bell-outline</v-icon>
              </v-badge>
            </v-btn>
          </div>
        </div>
      </div>

      <v-menu offset-y>
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            :ripple="false"
            v-bind="attrs"
            text
            class="text-capitalize"
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
      <v-avatar
        size="40"
        color="deep-purple lighten-4"
        style="border-radius: 5px"
      >
        <span class="purple--text title text--darken-4">AJ</span>
      </v-avatar>
    </v-app-bar>
    <v-main>
      <v-container
        fluid
        style="background-color: #232946"
        class="fill-height pt-0"
      >
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
          to: '/dashboard-second',
        },
        {
          icon: 'mdi-square-edit-outline',
          title: 'My Articles',
          to: '/inspire',
        },
        {
          icon: 'mdi-account-group-outline',
          title: 'Inbox',
          to: '/inspire',
        },
        {
          icon: 'mdi-cog-outline',
          title: 'Post Plan',
          to: '/inspire',
        },
        {
          icon: 'mdi-file-document-outline',
          title: 'Earning',
          to: '/inspire',
        },
        {
          icon: 'mdi-cog-outline',
          title: 'Settings',
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
<style>
.radius-active-class {
  border-radius: 5px;
}
</style>
