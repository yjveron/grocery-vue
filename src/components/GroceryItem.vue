<template>
    <div class="grocery-item" v-bind:class="{'is-completed':item.completed}">
        <p>
            <input type="checkbox" v-on:change="markCompleted">
            {{item.title}}
            <button v-on:click="$emit('remove-item', item.id)" class="remove">x</button>
        </p>
    </div>
</template>

<script>
export default {
    name: "GroceryItem",
    props: ["item"],
    methods: {
        markCompleted() {
            this.item.completed = !this.item.completed;
        }
    }
}
</script>

<style scoped>
    .grocery-item{
        background: #f4f4f4;
        padding: 10px;
        border-bottom: 1px #ccc solid;
    }

    .is-completed {
        text-decoration: line-through;
    }

    .remove {
        background: #ff0000;
        color: #fff;
        border: none;
        padding: 5px 9px;
        border-radius: 50%;
        cursor: pointer;
        float: right;
    }
</style>