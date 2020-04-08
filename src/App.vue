<template>
  <div id="app">
    <div class="container mx-auto">
      <h1 class="text-4xl">Vue Component Showcase</h1>
      <Navbar :value="tabs"></Navbar>
      <component v-for="tab in tabs" v-bind:key="tab.name" :is="tab.is" v-show="tab.isActive"></component>
    </div>
  </div>
</template>

<script>
import Navbar from "./components/Navbar";
import Todos from "./components/tabs/Todos";
import Cards from "./components/tabs/Cards";
import Repeaters from "./components/tabs/Repeaters";

export default {
  name: "App",
  components: { Navbar, Todos, Cards, Repeaters },
  data() {
    return {
      tabs: [
        { name: "Todo", is: "Todos", isActive: true },
        { name: "Cards", is: "Cards", isActive: false },
        { name: "Repeaters", is: "Repeaters", isActive: false }
        // { name: "Profile Small", is: "Repeaters", isActive: false },
        // { name: "Profile Large", is: "Repeaters", isActive: false }
      ]
    };
  }
};
</script>
