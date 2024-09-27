<script setup>
defineProps({
    collapse: {
        type: Array,
    }
})

const toggle = (item) => {
    item.isCollapsed = !item.isCollapsed
}
</script>

<template>
    <div>
        <ul class="relative">
            <li v-for="(item, index) in collapse" :key="index" >
                <div class="flex items-center gap-1 cursor-pointer" @click="toggle(item)">
                    <span v-if="item.children">
                        <Icon :name="item.isCollapsed ? 'eva:arrow-down-fill' : 'eva:arrow-up-fill'" />
                    </span>
                    <span>{{item.label}}</span>
                </div>
                <TreeCollapse v-if="item.children && !item.isCollapsed" :collapse="item.children" />
            </li>
        </ul>
    </div>
</template>