<script setup >
      import { storeToRefs } from 'pinia';
      import { useUserStore } from '../stores/user'
      
      const { theme , user } = storeToRefs(useUserStore())


</script>

<template>
<v-main>
<v-container fluid >
  <v-card
    class="mx-auto"
    max-width="434"
    rounded="0"
  >
    <v-img
      height="100%"
      cover
      src="https://cdn.vuetifyjs.com/images/cards/server-room.jpg"
    >
      <v-avatar
        
        size="150"
        rounded="0"
      >
        <v-img cover :src="user.avatar"></v-img>
      </v-avatar>
      <v-list-item
        class="text-white"
        :title = 'user.fname + " " + user.lname'  
        :subtitle = user.email
      ></v-list-item>
    </v-img>
  </v-card>
</v-container>
</v-main>
</template>

<style>

</style>
