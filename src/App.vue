<template>
  <div class="container-fluid">
    <div class="bg-info mt-2 p-2 text-white">
      <div>Imię: {{ name }}</div>
      <div>Hasło: {{ password }}</div>
      <div>Szczegóły: {{ details }}</div>
    </div>
    <div class="bg-primary m-2 p-2 text-white">
      <div class="form-group">
        <label>Imię</label>
        <input class="form-control" v-model="name"/>
      </div>
      <div class="form-group">
        <label>Hasło</label>
        <input type="password" class="form-control" v-model="password"/>
      </div>
      <div class="form-group">
        <label>Szczegóły</label>
        <textarea class="form-control" v-model="details"/>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'MyComponent',
    data() {
      return {
        name: "Janek",
        password: "hasło",
        details: "Ma uprawnienia administracyjne"
      }
    }
  }
</script>
