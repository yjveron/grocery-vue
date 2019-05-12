<template>
    <div>
        <form @submit="addGroceryItem">
            <input type="text" v-model="title" name="title" placeholder="Add List...">
            <input type="submit" value="Submit" class="btn">
        </form>
    </div>
</template>

<script>
import uuid from 'uuid';

export default {
    name: "AddGroceryItem",
    data() {
        return {
            title: ''
        }
    },
    methods: {
        addGroceryItem(e) {
            e.preventDefault();
            const newItem = {
                id: uuid.v4(),
                title: this.title,
                completed: false
            }
            this.$emit('add-grocery-item', newItem);

            this.title = '';
        }
    }
}
</script>


<style scoped>
form {
    display: flex;
}
input[type="text"]{
    flex: 10;
    padding: 5px;
}
input[type="submit"]{
    flex: 2;
}
</style>
