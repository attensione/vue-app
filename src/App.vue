<template>
    <img alt="Vue logo" src="./assets/logo.png">
    <h1>Welcome to Your Vue.js App</h1>
    <div class="container pt-3">
        <DataTable v-bind:houses="houses" v-bind:mounts="mounts" v-bind:specs="specs" />
    </div>
</template>

<script>
    /* eslint-disable */
    import 'bootstrap/dist/css/bootstrap.css';
    //import 'bootstrap/dist/js/bootstrap.js';
    //import * as bootstrap from 'bootstrap';

    import DataTable from './components/DataTable.vue'

    export default {
      data() {
        return {
            houses: [
                { id: 1, mount: 'tree', spec: 'bird', price: 250 },
                { id: 2, mount: 'tree', spec: 'squirrel', price: 350 },
                { id: 3, mount: 'ground', spec: 'hare', price: 1500 },
                { id: 4, mount: 'ground', spec: 'hedgehog', price: 200 },
                { id: 5, mount: 'ground', spec: 'lynx', price: 1600 },
            ],
            mounts: [ 'ground', 'tree' ],
            specs: [ 'dog', 'cat', 'bird' ]
        }
      },
      components: {
        DataTable
      }
    }
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
