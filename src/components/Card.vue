<template>
  <div class="bg-gray-200 rounded shadow-lg relative mb-12">
    <div class="absolute" style="top: -1rem; right: -1rem">
      <slot name="icon"></slot>
    </div>

    <slot name="image"></slot>

    <h3 class="text-2xl mb-4 px-5 pt-5">
      <slot name="header"></slot>
    </h3>

    <div class="px-5 py-2">
      <slot></slot>
    </div>

    <div class="text-right px-5 py-2 pb-5">
      <slot name="footer"></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    icon: String
  }
};
</script>

<style>
</style>