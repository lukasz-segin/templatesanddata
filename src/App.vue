<template>
  <div class="container-fluid">
    <h2 class="btn-primary text-white text-center p-3">
      Produkty
    </h2>
    <table class="table table-sm table-bordered table-striped text-left">
      <tr>
        <th>Nazwa</th>
        <th>Cena</th>
      </tr>
      <tbody>
      <tr v-for="p in products" v-bind:key="p.name">
        <td>{{ p.name }}</td>
        <td>{{ p.price | currency }}</td>
      </tr>
      </tbody>
    </table>
    <div class="text-center">
      <button v-on:click="handleClick" class="btn btn-primary">
        Wciśnij mnie
      </button>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'MyComponent',
    data() {
      return {
        products: [
          {name: "Kajak", price: 275},
          {name: "Kamizelka ratunkowa", price: 48.95},
          {name: "Piłka nożna", price: 19.50}
        ]
      }
    },
    filters: {
      currency(value) {
        return new Intl.NumberFormat("pl-PL",
            { style: "currency", currency: "PLN",}).format(value);
      }
    },
    methods: {
      handleClick() {
        this.products.push(this.products.shift());
      }
    }
    // document.querySelector("tbody > tr").id = "tagged"
  }
</script>
<style>
  #tagged {
    background-color: coral;
  }
</style>
