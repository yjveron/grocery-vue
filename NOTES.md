# grocery-vue

## Creating a Component
1. Create a .vue file under the components folder
2. Write down template markup including script and style
3. Establish export under <script> tags of that vue file
    ```
        export default {
            name: "GroceryList"
        }
    ```
4. Under App.vue, import the newly created component
    ```
        import GroceryList from './components/GroceryList';
    ```
    and
    ```
        export default {
        name: 'app',
        components: {
            GroceryList
        },
    ```
5. Attach App.vue's items data to the GroceryList component through v-bind
    ```
        <GroceryList v-bind:items="items" />
    ```