<template>
  <div class="container mx-auto w-4/5 py-5 my-16 bg-gray-200 rounded shadow-lg">
    <div class="flex justify-between">
      <h3 class="text-2xl">Todos</h3>
      <button
        class="text-xs bg-transparent hover:bg-gray-500 text-gray-700 font-semibold hover:text-white py-2 px-4 border border-gray-500 hover:border-transparent rounded"
        @click="cleanup"
      >Clean up</button>
    </div>
    <ul class="w-100 my-4">
      <li
        v-for="(todo, index) in todos"
        :key="todo.input"
        :class="[...listItemStyle, todo.done ? 'border-solid' : 'border-none']"
      >
        <span :class="['font-bold', todo.done ? 'line-through' : '']">{{todo.input}}</span>
        <button
          class="text-xs bg-transparent hover:bg-green-500 text-green-700 font-semibold hover:text-white py-2 px-4 border border-green-500 hover:border-transparent rounded"
          @click="done(index)"
          v-if="!todo.done"
        >Done!</button>
        <button
          class="text-xs bg-transparent hover:bg-green-500 text-green-700 font-semibold hover:text-white py-2 px-4 border border-green-500 hover:border-transparent rounded"
          @click="undo(index)"
          v-if="todo.done"
        >Undo!</button>
      </li>
    </ul>

    <form @submit="addTodo">
      <div class="mb-4">
        <label
          class="block text-gray-700 text-sm font-bold mb-2"
          for="username"
        >What needs to be done?</label>
        <input
          class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
          id="todo"
          type="text"
          placeholder="Enter to submit..."
          v-model="input"
        />
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todos: [
        { input: "Walk the dog", done: false },
        { input: "Buy toilet paper", done: false }
      ],
      input: "",
      listItemStyle: [
        "bg-gray-400",
        "p-3",
        "mb-2",
        "rounded",
        "flex",
        "justify-between",
        "border-solid",
        "border-l-4",
        "border-green-500"
      ]
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      if (this.input === "") return;
      this.todos.push({
        input: this.input,
        done: false
      });
      this.input = "";
    },
    done(index) {
      this.todos[index].done = true;
    },
    undo(index) {
      this.todos[index].done = false;
    },
    cleanup() {
      this.todos = this.todos.filter(todo => !todo.done);
    }
  }
};
</script>

<style>
</style>