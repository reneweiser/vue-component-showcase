<template>
  <div class="container mx-auto w-4/5 py-5 my-16">
    <Card>
      <template v-slot:header>Simple Card</template>
      <p>Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua.</p>
    </Card>
    <Card>
      <template v-slot:icon>
        <img src="https://via.placeholder.com/64?Text=Icon" class="rounded-full" />
      </template>
      <template v-slot:header>Card with icon and Call-to-Action</template>
      <p>Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua.</p>
      <template v-slot:footer>
        <button
          class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
        >Call to action</button>
      </template>
    </Card>
    <Card class="overflow-hidden">
      <template v-slot:image>
        <img src="https://via.placeholder.com/512x128?Text=Icon" class="w-full" />
      </template>
      <template v-slot:header>Card with image</template>
      <p>Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua.</p>
    </Card>
  </div>
</template>

<script>
import Card from "../Card";
export default {
  components: { Card }
};
</script>

<style>
</style>