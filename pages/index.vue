<template>
  <div>
    <h1>This is Index page</h1>
    <v-form ref="form">
      <v-card max-width="500" variant="outlined">
        <v-card-item>
          <v-file-input variant="outlined" label="File input" accept="image/*" v-model="files"></v-file-input>
        </v-card-item>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn variant="outlined" @click="submit">
            Button
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-form>
  </div>
</template>

<script setup lang="ts">
const config = useRuntimeConfig();
const {apiUrl} = config.public;
const files = ref([]);
const submit = async () => {
  const file = files.value[0];
  const form = new FormData();
  form.append('file', file, 'file.png');
  const {data} = await useFetch(`${apiUrl}/upload`, {
    method: 'POST',
    body: form
  })
  console.log(data.value)
}
</script>