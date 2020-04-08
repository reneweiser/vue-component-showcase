<template>
  <div class="mb-4">
    <label class="block text-gray-700 text-sm font-bold mb-2">{{label}}</label>
    <div class="relative">
      <select
        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
        id="grid-state"
        v-model="proxyValue"
      >
        <option value="0">Line of text</option>
        <option value="1">Text area</option>
      </select>
      <div
        class="pointer-events-none absolute inset-y-0 right-0 flex items-center px-2 text-gray-700"
      >
        <svg class="fill-current h-4 w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20">
          <path d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z" />
        </svg>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    label: String,
    value: String
  },
  computed: {
    proxyValue: {
      get() {
        return this.value;
      },
      set(newVal) {
        this.$emit("input", newVal);
      }
    }
  }
};
</script>

<style>
</style>