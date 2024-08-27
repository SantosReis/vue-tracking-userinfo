<script setup>
import DataTable from '../components/DataTable.vue'
import { onMounted, ref } from 'vue'

const items = ref([])
const API_URL = import.meta.env.VITE_API_URL

onMounted(async () => {
  const response = await fetch(API_URL + `/api/trackinginfo/`)
  items.value = await response.json()
})
</script>

<template>
  <main>
    <div class="p-8 bg-gray-100 min-h-screen">
      <DataTable :items="items.data" />
    </div>
  </main>
</template>
