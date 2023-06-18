<template>
  <div>
    <h1>Hello from params id with : {{ route.params.id }}</h1>
    <h1>Hello from query with : {{ route.query }}</h1>
  </div>
</template>

<script setup>
const route = useRoute()
</script>