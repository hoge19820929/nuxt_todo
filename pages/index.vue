<template>
  <div class="container" id="app">
    <div>
      <Logo />
      <h1 class="title">TODO</h1>
      <input type="text" v-model="newItem" />
      <form v-on:submit.prevent>
        <button v-on:click="addItem">add</button>
      </form>
      <li v-for="todo in todos">{{ todo.item }}</li>
      <h2 class="subtitle">TODO</h2>
    </div>
  </div>
</template>

<script>
import Logo from "~/components/Logo.vue";

export default {
  components: {
    Logo
  },
  data() {
    return {
      newItem: "",
      todos: []
    };
  },
  methods: {
    addItem: function(event) {
      var todo = {
        item: this.newItem
      };
      this.todos.push(todo);
    }
  }
};
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
