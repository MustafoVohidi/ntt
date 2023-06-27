<template>
    <div>
        <div class="content">
            <AppList :data="dataFromJSON"></AppList>
        </div>
        <div class="modal-foot">
            <button class="success" @click="select">
                Ок
            </button>
        </div>
    </div>
</template>
<script setup>
import AppList from '@/components/AppList.vue';
import { useStore } from 'vuex';
import { computed, onMounted } from 'vue'

const emits = defineEmits(['close'])
const store = useStore()
const dataFromJSON = computed(() => store.state.dataFromJSON)
const getData = () => store.dispatch("getData")
const select = () => {
    emits("close")
}
onMounted(async () => {
    await getData()
    console.log(dataFromJSON.value)
})
</script>
<style lang="scss">
.success {
    border: 1px solid #67c23a;
    background: #f0f9eb;
    color: #67c23a;

    &:hover {
        background: #67c23a;
        color: #fff;
    }
}
</style>