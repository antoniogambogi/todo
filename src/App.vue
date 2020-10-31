<template>
  <div class="" id="app">
    <div class="container grid-xs py-2">
      <img class="img-responsive img-logo" src="@/assets/logo.png" alt="logo Vue">
      <form @submit.prevent="addTodo(todo)">
        <div class="input-group">
          <input type="text" v-model="todo.description" class="form-input" placeholder="Novo todo">
          <button class="btn btn-primary input-group-btn">Adicionar</button>
        </div>
      </form>
      <div class="todo-list">
        <div class="tile" v-for="t in todos" :key="t.id">
          <div class="tile-icon">
            <div>
              <i class="icon icon-time centered"></i>
            </div>
          </div>
          <div class="tile-content">
            <p class="tile-subtitle">{{ t.description }}</p>
          </div>
          <div class="tile-action">
            <button class="btn btn-link">Concluído</button>
            <button class="btn btn-link">
              <span class="text-error">Remover</span>
            </button>
        </div>
      </div>
    </div>
  </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return { todos: [], todo: { checked: false } };
  },
  methods: {
    addTodo(todo) {
      todo.id = Date.now();
      this.todos.push(todo);
      this.todo = { checked: false };
    },
  },
};
</script>

<style scoped>
.img-logo {
  max-width: 100px;
  margin: 20px auto 20px auto;
}

.todo-list {
  padding-top: 1.5rem;
}
</style>
