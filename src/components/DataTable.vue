<script setup>
defineProps({
  items: {
    type: Array,
    required: true,
  },
})
</script>

<template>
  <div class="bg-white relative border rounded-lg">
    <div class="w-full text-sm text-left text-gray-500">
      <thead class="text-xs text-gray-700 uppercase bg-gray-50">
        <tr>
          <th class="px-4 py-3">InternalClient</th>
          <th class="px-4 py-3">Client</th>
          <th class="px-4 py-3">Module</th>
          <th class="px-4 py-3">Language</th>
          <th class="px-4 py-3">Mobile</th>
          <th class="px-4 py-3">Date</th>
          <th class="px-4 py-3">
            <span class="sr-only">Actions</span>
          </th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in items" :key="item.id">
          <td class="px4 py3 font-medium text-gray-900">
            {{ item.internal_client }}
          </td>
          <td class="px4 py3 font-medium text-gray-900">{{ item.client }}</td>
          <td class="px4 py3">{{ item.module }}</td>
          <td class="px4 py3">{{ item.language }}</td>
          <td class="px4 py3">{{ item.mobile }}</td>
          <td class="px4 py3">
            {{ item.created_at }}
          </td>
          <td class="px-4 py-3 flex item-center justify-end">Details</td>
        </tr>
      </tbody>
    </div>
  </div>
</template>
