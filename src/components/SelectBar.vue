<script>
import { store } from '../data/store';
export default {
    name: 'SelectBar',
    data() {
        return {
            store,
            type: ''
        }
    },
    emits: ['change-option']
}
</script>


<template>
    <select v-model="type" @change="$emit('change-option', type)" class="container form-select">
        <option value="restart"> - </option>
        <option v-for="(type) in store.optionTypes" :key="type" :value="type"> {{ type }}
        </option>
    </select>
</template>


<style scoped lang="scss">
select {
    width: 25%;
    margin-bottom: 30px;
}
</style>