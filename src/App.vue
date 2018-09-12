<template>
  <v-app class="blue darken-2">
    <v-navigation-drawer
      persistent
      :mini-variant="miniVariant"
      :clipped="clipped"
      v-model="drawer"
      enable-resize-watcher
      fixed
      app
      class="blue-grey"
    >
      <v-list>
        <v-list-tile>
            <br>
            <img :src="Logo" height="40">
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar
      flat
      app
      :clipped-left="clipped"
      dark
      class="transparent"
    >
      <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
      <v-spacer></v-spacer>
      <v-toolbar-title>
          <div style="text-align: center; font-size: 16px;">
                  MyENV <br>
                  Current Location <i class="fas fa-chevron-down"></i>
          </div>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn icon @click.stop="rightDrawer = !rightDrawer">
          <i class="fas fa-bell fa-lg"></i>
      </v-btn>
    </v-toolbar>
    <v-content>
      <Home/>
    </v-content>
    <v-navigation-drawer
      temporary
      :right="right"
      v-model="rightDrawer"
      fixed
      app
    >
      <v-list>
        <v-list-tile>
          <v-list-tile-title>Notifications</v-list-tile-title>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
  </v-app>
</template>

<script>
import Logo from './assets/logo.png'
import Home from './components/home'

export default {
  name: 'App',
  components: {
    Home
  },
  data () {
    return {
      Logo,
      clipped: false,
      drawer: true,
      fixed: false,
      miniVariant: false,
      right: true,
      rightDrawer: false,
    }
  },
    computed: {
    }
}
</script>
