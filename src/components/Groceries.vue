<template>
    <div>
        <div v-for="item in items" v-bind:key="item.id">
            <GroceryItem v-bind:item="item" v-on:remove-item="$emit('remove-item', item.id)"/>
        </div>
    </div>
</template>

<script>
import GroceryItem from './GroceryItem.vue';


export default {
    name: "Groceries",
    components: {
        GroceryItem
    },
    props: ["items"]
}
</script>

<style scoped>

</style>