<template>
  <v-app>
    <v-toolbar dark class="primary">
      <v-toolbar-title>
        <router-link to="/" tag="span" style="cursor: pointer">Home page</router-link>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items>
        <v-btn
          flat
          v-for="item in menuItems"
          :key="item.title"
          :to="item.link">
          <v-icon left dark>{{ item.icon }}</v-icon>
          {{ item.title }}
        </v-btn>
      </v-toolbar-items>
    </v-toolbar>
    <main>
      <router-view></router-view>
    </main>
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        menuItems: [
          {icon: 'face', title: 'Sign in', link: '/signin'},
          {icon: 'lock_open', title: 'Sign up', link: '/signup'},
          {icon: 'clear', title: 'Log out', link: '/logout'}
        ]
      }
    }
  }
</script>
