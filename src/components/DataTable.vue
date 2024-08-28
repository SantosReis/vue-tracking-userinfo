<script setup>
defineProps({
  items: {
    type: Array,
    required: true,
  },
})

import { shallowRef } from 'vue'

const API_URL = import.meta.env.VITE_API_URL
const excel_export = shallowRef(API_URL + `/api/export/`)
</script>

<template>
  <div class="bg-white relative border round-lg">
    <div class="flex items-center justify-end text-sm font-semibold">
      <a
        :href="excel_export"
        class="bg-gray-300 hover:bg-gray-400 text-gray-800 font-bold m-3 py-2 px-4 rounded inline-flex items-center"
      >
        <svg
          class="fill-current w-4 h-4 mr-2"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 20 20"
        >
          <path d="M13 8V2H7v6H2l8 8 8-8h-5zM0 18h20v2H0v-2z" />
        </svg>
        <span>Download</span>
      </a>
    </div>
    <table class="w-full text-sm text-left text-gray-500">
      <thead class="text-xs text-gray-700 uppercase bg-gray-50">
        <tr>
          <th class="px-4 py-3">Internal Client</th>
          <th class="px-4 py-3">Client</th>
          <th class="px-4 py-3">Module</th>
          <th class="px-4 py-3">Language</th>
          <th class="px-4 py-3">URL</th>
          <th class="px-4 py-3">Date</th>
          <th class="px-4 py-3">Width</th>
          <th class="px-4 py-3">Height</th>
          <th class="px-4 py-3">Browser</th>
          <th class="px-4 py-3">Browser Version</th>
          <th class="px-4 py-3">Java</th>
          <th class="px-4 py-3">Mobile</th>
          <th class="px-4 py-3">OS</th>
          <th class="px-4 py-3">OSVersion</th>
          <th class="px-4 py-3">Cookies</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in items" :key="item.id">
          <td class="px-4 py-3 font-medium text-gray-900">
            {{ item.internal_client }}
          </td>
          <td class="px-4 py-3 font-medium text-gray-900">{{ item.client }}</td>
          <td class="px-4 py-3">{{ item.module }}</td>
          <td class="px-4 py-3">{{ item.language }}</td>
          <td class="px-4 py-3">{{ item.url }}</td>
          <td class="px-4 py-3">
            {{ item.created_at }}
          </td>
          <td class="px-4 py-3">{{ item.width }}</td>
          <td class="px-4 py-3">{{ item.height }}</td>
          <td class="px-4 py-3">{{ item.browser }}</td>
          <td class="px-4 py-3">{{ item.browser_version }}</td>
          <td class="px-4 py-3">{{ item.java ? 'Yes' : 'No' }}</td>
          <td class="px-4 py-3">{{ item.mobile ? 'Yes' : 'No' }}</td>
          <td class="px-4 py-3">{{ item.os }}</td>
          <td class="px-4 py-3">{{ item.osversion }}</td>
          <td class="px-4 py-3">{{ item.cookies ? 'Yes' : 'No' }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
