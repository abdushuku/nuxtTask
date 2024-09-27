<script setup>
defineProps({
    tableData: {
        type:Array
    }
})
</script>

<template>
  <div class="m-3">
     <table class="custom-table w-full border-collapse p-2 max-w-[1000px]">
    <thead>
      <tr class="text-left">
        <th class="px-4 py-2">
          <div class="flex items-center gap-2">
            <Icon name="wpf:name" />
            <span>Name</span>
          </div>
        </th>
        <th class="px-4 py-2">
          <div class="flex items-center gap-2">
            <Icon name="game-icons:ages" />
            <span>Age</span>
          </div>
        </th>
        <th class="px-4 py-2">
          <div class="flex items-center gap-2">
            <Icon name="mdi:address-marker" />
            <span>Address</span>
          </div>
        </th>
        <th class="px-4 py-2">
          <div class="flex items-center gap-2">
            <Icon name="mdi:tags" />
            <span>Tags</span>
          </div>
        </th>
        <th class="px-4 py-2">
          <div class="flex items-center gap-2">
            <Icon name="grommet-icons:action" />
            <span>Action</span>
          </div>
        </th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(data, index) in tableData" :key="index" class="border-b">
        <td class="px-4 py-2">{{ data.name }}</td>
        <td class="px-4 py-2">{{ data.age }}</td>
        <td class="px-4 py-2">{{ data.address }}</td>
        <td class="px-4 py-2">
          <div v-for="(tag, tagIndex) in data.tags" :key="tagIndex" class="flex  gap-2">
                <span class="p-1 uppercase text-green-300 border border-green-300 rounded w-max" :class="{'text-red-500 border-red-500': tag.status === 'loser'}">{{ tag.status }}</span>
                <span class="text-blue border border-blue  p-1 rounded" v-if="tag.profession">{{ tag.profession }}</span> 
            </div>
        </td>
        <td class="px-4 py-2 flex items-center gap-2 text-blue">
           <span class="cursor-pointer">Ivite - {{data.name}}</span>
            <button class="cursor-pointer">delete</button>
            <span class="flex items-center cursor-pointer"> More actions <Icon name="eva:arrow-ios-downward-outline" /></span>
        </td>
      </tr>
    </tbody>
  </table>
  </div>
</template>


