<template>
  <div>
    <v-container fluid>
      <v-layout>
        <!-- <v-app-bar :elevation="1" color="info">
          <template v-slot:prepend>
            <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
          </template>
          <v-app-bar-title>Pokemon</v-app-bar-title>
        </v-app-bar> -->

        <Navigations v-model="drawer" />

        <v-main>
          <slot />
        </v-main>

      </v-layout>
    </v-container>
  </div>
</template>

<script setup lang="ts">
const drawer = ref(true);
</script>