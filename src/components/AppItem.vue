<template>
    <div v-if="porps.data.child" class="has-child">
        {{ porps.data.name }}
        <AppList 
        :data=" porps.data.child"
        />
    </div>
    <div class="item">
        {{ porps.data.name }}
    </div>
</template>
<script setup>
import AppList from './AppList.vue';
const props=defineProps({
    data:{
        type:Object,
        default:{}
    }
})
</script>
<style lang="scss"></style>