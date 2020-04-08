<template>
  <div class="mb-4">
    <label class="block text-gray-700 text-sm font-bold mb-2">{{label}}</label>
    <input
      class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
      type="text"
      :placeholder="placeholder"
      v-model="proxyValue"
    />
  </div>
</template>

<script>
export default {
  props: {
    label: String,
    placeholder: String,
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