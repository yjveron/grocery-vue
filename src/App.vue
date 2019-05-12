<template>
  <div id="app">
    <Header />
    <AddGroceryItem v-on:add-grocery-item="addGroceryItem" />
    <Groceries v-bind:items="items" v-on:remove-item="removeItem"/>
  </div>
</template>

<script>
import Header from './components/layout/Header';
import Groceries from './components/Groceries';
import AddGroceryItem from './components/AddGroceryItem';
import axios from 'axios';

export default {
  name: 'app',
  components: {
    Header,
    Groceries,
    AddGroceryItem
  },
  data() {
    return {
      items: []
    }
  },
  methods: {
    removeItem(id) {
      this.items = this.items.filter(item => item.id !== id);
      // Loops through and returns an array based on the condition
      // Not really deleting, just filtering out
    },
    addGroceryItem(newItem) {
      this.items = [...this.items, newItem];
    }
  },
  created() {
    axios.get('https://jsonplaceholder.typicode.com/todos?_limit=10')
    .then(res => this.items = res.data)
    .catch(err => console.log(err));
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}

    .btn {
        display: inline-block;
        border: none;
        background: #555;
        color: #fff;
        padding: 7px 20px;
        cursor: pointer;
    }

    .btn:hover{
        background: #555;
    }

/* #app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
