<template>
  <div class="container-fluid text-center">
    <div class="bg-primary text-white m-2 p-3">
      <h3>Produkt: {{ name }}</h3>
    </div>
    <button v-on:click="handleClick" class="btn btn-primary">
      Wciśnij mnie
    </button>
  </div>
</template>

<script>
  export default {
    name: 'MyComponent',
    data() {
      return {
        name: "Kamizelka ratunkowa"
      }
    },
    methods: {
      handleClick() {
        // nie rób nic
      }
    }
  }
</script>
<style>
  h3:first-child {
    background-color: aquamarine;
    padding: 10px;
    color: black;
  }
</style>