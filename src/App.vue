<template>
  <div class="container-fluid">
    <h3 class="bg-primary text-white text-center mt-2 p-2">{{ message }}</h3>
    <table class="table table-sm table-striped table-bordered">
      <tr>
        <th>Indeks</th>
        <th>Nazwa</th>
        <th>Akcje</th>
      </tr>
      <tr v-for="(name, index) in names" v-bind:key="name">
        <td>{{ index }}</td>
        <td>{{ name }}</td>
        <td>
          <button class="btn btn-sm bg-primary text-white"
                  v-on:click="handleClick(name)"
                  v-on:mousemove="handleMouseEvent(name, $event)"
                  v-on:mouseleave="handleMouseEvent(name, $event)"
          >
            Wybierz
          </button>
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
  export default {
    name: 'MyComponent',
    data() {
      return {
        counter: 0,
        message: "Gotowy",
        names: ["Kajak", "Kamizelka ratunkowa", "Piłka nożna", "Stadion"]
      }
    },
    methods: {
      handleClick(name) {
        this.message = `Wybierz: ${name}`;
      },
      handleMouseEvent(name, $event) {
        if ($event.type === "mousemove") {
          this.message = `Ruch w ${name} ${this.counter++}`;
        } else {
          this.counter = 0;
          this.message = "Gotowy";
        }
      }
    }
  }
</script>
