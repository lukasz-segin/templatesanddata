<template>
  <div class="container-fluid">
    <div class="bg-primary text-white m-2 p-3 text-center">
      <h3 v-on:click="handleEvent('Piłka nożna', $event)">{{ name }}</h3>
    </div>

    <div class="bg-primary text-white m-2 p-3 text-center">
      <h3 v-on:click="handleEvent('Stadion', $event)">{{ name }}</h3>
    </div>
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
      handleEvent(name, $event) {
        this.name = `${name} - ${$event.type}`;
      }
    }
  }
</script>
