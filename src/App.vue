<template>
  <div class="container-fluid">
    <div class="bg-info mt-2 p-2 text-white">
      Wartość: {{ dataValue }}
    </div>
    <div class="bg-primary m-2 p-2 text-white">
      <div class="form-check">
        <label class="form-check-label">
          <input class="form-check-input" type="checkbox" v-on:change="handleChange" v-bind:checked="dataValue" />
          Wartość danych
        </label>
      </div>
    </div>
    <div class="text-center m-2">
      <button class="btn btn-secondary" v-on:click="reset">
        Reset
      </button>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'MyComponent',
    data() {
      return {
        dataValue: false
      }
    },
    methods: {
      reset() {
        this.dataValue = false;
      },
      handleChange($event) {
        this.dataValue = $event.target.checked;
      }
    }
  }
</script>
