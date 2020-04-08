<template>
  <Card>
    <template v-slot:header>Form Builder</template>
    <form class="mb-4">
      <TextInput v-model="fieldLabel" label="Field Label"></TextInput>
      <Select v-model="fieldValue" label="Field Type"></Select>
      <button
        @click="addField"
        class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
      >Add</button>
    </form>

    <div class="bg-gray-300 p-2 rounded">
      <code>
        <pre>{{codeString}}</pre>
      </code>
    </div>
  </Card>
</template>

<script>
import Card from "./Card";
import TextInput from "./TextInput";
import Select from "./Select";
export default {
  components: { Card, TextInput, Select },
  computed: {
    codeString() {
      return JSON.stringify(this.code, null, 2);
    }
  },
  data() {
    return {
      code: {
        form: []
      },
      fieldLabel: "",
      fieldValue: "0"
    };
  },
  methods: {
    addField(e) {
      e.preventDefault();
      this.code.form.push({
        label: this.fieldLabel,
        value: this.fieldValue
      });
      this.fieldLabel = "";
      this.fieldValue = "0";
    }
  }
};
</script>

<style>
</style>