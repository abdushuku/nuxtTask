<script setup>
const collapse = ref([
  {
    label: "item 1",
    children: [
      {
        label: "item 1-1",
        children: [
          {
            label: "item 1-1-1"
          }
        ]
      }
    ],
    isCollapsed: true
  },
  {
    label: "item 2",
    children: [
      {
        label: "item 2-1",
        children: [
          {
            label: "item 2-1-1"
          }
        ]
      },
      {
        label: "item 2-2",
        children: [
          {
            label: "item 2-2-1"
          }
        ]
      }
    ],
    isCollapsed: true
  }
]);



const tableData = ref([
  {
    key: 1,
    name: 'John Brown',
    age: 32,
    address: 'New York No. 1 Lake Park',
    tags: [{
      status: 'nice',
      profession:'Developer'
    }],
  },
  {
    key: 2,
    name: 'Jim Green',
    age: 42,
    address: 'London No. 1 Lake Park',
    tags: [{
      status: 'loser',
    }],
  },
  {
    key: 3,
    name: 'Joe Black',
    age: 32,
    address: 'Sidney No. 1 Lake Park',
    tags: [{
      status: 'cool',
      profession:'Teacher'
    }],
  }
]);
</script>

<template>
  <div class="w-full">
    <TreeCollapse :collapse="collapse" class="m-3" />
    <Table :tableData="tableData" class="pt-5"/>
  </div>
</template>
