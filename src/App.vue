<template>
  <div id="app">
    <GroceryItems v-bind:items="items"/>
  </div>
</template>

<script>
import GroceryItems from './components/GroceryItems';

export default {
  name: 'app',
  components: {
    GroceryItems
  },
  data() {
    return {
      items: [
        {
          id: 1,
          name: 'Apples',
          purchased: false
        },
        {
          id: 2,
          name: 'Oranges',
          purchased: false
        },
        {
          id: 3,
          name: 'Mangoes',
          purchased: false
        }
      ]
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
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
