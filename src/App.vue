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
    import 'bootstrap/dist/js/bootstrap.js';
    import DataTable from './components/DataTable.vue'

    export default {
      data() {
        return {
            houses: [
                { id: 1, mount: 'tree', spec: 'bird', price: 1000 },
                { id: 2, mount: 'ground', spec: 'dog', price: 2000 },
                { id: 3, mount: 'ground', spec: 'cat', price: 1500 },
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
