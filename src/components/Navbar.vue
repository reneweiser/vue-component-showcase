<template>
  <ul class="flex border-b mt-5">
    <li class="-mb-px mr-1" v-for="tab in value" v-bind:key="tab.name">
      <a
        :class="tab.isActive ? activeClasses : inactiveClasses"
        @click="setActive(tab.name)"
        type="button"
      >{{tab.name}}</a>
    </li>
  </ul>
</template>

<script>
export default {
  name: "Navbar",
  props: {
    value: Array
  },
  computed: {
    proxyValue: {
      get() {
        return this.value;
      },
      set(newVal) {
        this.proxyValue = newVal;
      }
    }
  },
  data() {
    return {
      activeClasses:
        "cursor-pointer bg-white inline-block border-l border-t border-r rounded-t py-2 px-4 text-blue-700 font-semibold",
      inactiveClasses:
        "cursor-pointer bg-white inline-block py-2 px-4 text-blue-500 hover:text-blue-800 font-semibold"
    };
  },
  methods: {
    setActive(name) {
      this.proxyValue.forEach(v => (v.isActive = v.name === name));
    }
  }
};
</script>

<style>
</style>