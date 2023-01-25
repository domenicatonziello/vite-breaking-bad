<script>
import { store } from '../data/store';
export default {
    name: 'SelectBar',
    data() {
        return {
            store
        }
    },
    emits: ['change-option']
}
</script>


<template>
    <select class="container form-select">
        <option v-for="(type) in store.optionTypes" @change="$emit('change-option', type)" :value="type"> {{ type }}
        </option>
    </select>
</template>


<style scoped lang="scss">
select {
    width: 25%;
    margin-bottom: 30px;
}
</style>