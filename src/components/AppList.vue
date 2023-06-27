<template>
    <div>
        <AppItem v-for="item in props.data" :key="item.id" :data="item" >

        </AppItem>
    </div>
</template>
<script setup>
import AppItem from '@/components/AppItem.vue';
import {onMounted} from "vue"
const props = defineProps({
    data: {
        type: Object,
        default: {}
    }
})
// onMounted(() => {
//     console.log(props.data, "data")
// })
</script>
<style lang="">
    
</style>