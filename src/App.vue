<template>
  <v-app class="frame">
    <v-navigation-drawer app>
      <!-- -->
    </v-navigation-drawer>

    <v-app-bar class="app-header-bar" app>
      <v-app-bar-nav-icon></v-app-bar-nav-icon>
      <v-toolbar-title>Music Order</v-toolbar-title>
      <v-spacer></v-spacer>
      <!-- <v-switch v-model="$vuetify.theme.dark" :dark="$vuetify.theme.dark">
        <span slot="label">
          <v-icon v-if="$vuetify.theme.dark">fas fa-moon</v-icon>
          <v-icon v-else>fas fa-sun</v-icon>
        </span>
      </v-switch> -->
      <!-- 最小化窗口 minimize the window -->
      <v-btn icon @click="minimizeTheWindow">
        <v-icon>fas fa-minus</v-icon>
      </v-btn>
      <!-- <v-btn icon>
        <v-icon>fas fa-clone</v-icon>
      </v-btn> -->
      <!-- fullscreen 全屏 -->
      <v-btn icon>
        <v-icon>fas fa-square</v-icon>
      </v-btn>
      <!-- 关闭窗口 close window -->
      <v-btn icon @click="closeApp">
        <v-icon>fas fa-times</v-icon>
      </v-btn>
    </v-app-bar>

    <!-- Sizes your content based upon application components -->
    <v-main>
      <!-- Provides the application the proper gutter -->
      <v-container fluid>
        <!-- If using vue-router -->
        <router-view></router-view>
      </v-container>
    </v-main>

    <v-footer app>
      <!-- -->
    </v-footer>
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue'
import { closeApp } from '@/background/app.background'
import './assets/scss/index.scss'

export default Vue.extend({
  name: 'App',

  // components: {
  // },

  data: () => ({
    //
    darkMode: true
  }),
  methods: {
    closeApp(): void {
      closeApp()
    },
    minimizeTheWindow(): void {
      console.log('minimizeTheWindow')
    },
    changeDarkMode(): void {
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark
    }
  }
})
</script>

<style lang="scss">
.app-header-bar {
  -webkit-app-region: drag;
}
</style>
