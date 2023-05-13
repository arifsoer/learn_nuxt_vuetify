<template>
  <div>
    <v-navigation-drawer :model-value="modelValue" @input="$emit('update:modelValue', $event.target.value)"
      location="left" permanent>
      <v-row justify="center" align-content="center">
        <v-col class="ma-3 d-flex justify-center">
          <v-list-item-title>Pokemon</v-list-item-title>
        </v-col>
      </v-row>
      <v-divider />
      <v-list>
        <v-list-item v-for="item in items" :key="item.value" @click="navAction(item.value)">
          {{ item.title }}
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script setup lang="ts">
defineProps(['modelValue'])
defineEmits(['update:modelValue'])

interface MenuItem {
  title: string;
  value: string;
}

const navAction = (value: string) => {
  navigateTo(value)
}

const items: MenuItem[] = [
  {
    title: 'Home',
    value: '/',
  },
  {
    title: 'Library',
    value: '/library'
  }
]
</script>