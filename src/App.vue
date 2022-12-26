     
     <script setup>
      import { RouterLink, RouterView } from 'vue-router'
      import { ref } from 'vue'
      import { storeToRefs } from 'pinia';
      import { useUserStore } from './stores/user'
      
      const { theme , user } = storeToRefs(useUserStore())
      const { onClick, login, logout } = useUserStore()
      
      </script>

<template>
  <v-app :theme="theme">
    <v-app-bar>
      <v-btn href="/">
        <v-app-bar-title>My App</v-app-bar-title>
      </v-btn>
      <v-spacer></v-spacer>
      <v-btn href="/about">About</v-btn>
      <v-btn :icon="theme === 'light' 
      ? 'mdi-weather-sunny' : 'mdi-weather-night'" 
      @click="onClick"></v-btn>
      <v-btn v-if="!user" icon="mdi-login" @click="login(2)" />
      <v-btn v-if="user" icon @click="logout()">
        <v-avatar>
          <v-img :src="user.avatar"></v-img>
        </v-avatar>
      </v-btn>
    </v-app-bar>
    <RouterView />
  </v-app>

</template>


<style scoped>

</style>
