<template>
  <div class="todo-list">
    <input
      type="text"
      placeholder="Tambah kegiatan..."
      v-model="newTodo"
      @keydown.enter="addTodo"
    />
    <div class="filter-container">
<<<<<<< HEAD
      <button :class="{ active: filter === 'all' }" @click="filter = 'all'">
        Semua
      </button>
      <button
        :class="{ active: filter === 'pending' }"
        @click="filter = 'pending'"
      >
        Belum Selesai
      </button>
=======
      <label for="filter-all">Semua</label>
      <input
        type="radio"
        id="filter-all"
        name="filter"
        v-model="filter"
        value="all"
        checked
      />
      <label for="filter-pending">Belum Selesai</label>
      <input
        type="radio"
        id="filter-pending"
        name="filter"
        v-model="filter"
        value="pending"
      />
>>>>>>> a366d0e045f979b231dc5fd9f74ce7443c87f120
    </div>
    <ul>
      <todo-item
        v-for="(todo, index) in filteredTodos"
        :key="index"
        :todo="todo"
        @toggle-done="toggleDone(index)"
        @delete-todo="deleteTodo(index)"
<<<<<<< HEAD
        @edit-todo="editTodo(index, $event)"
=======
>>>>>>> a366d0e045f979b231dc5fd9f74ce7443c87f120
      />
    </ul>
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";

export default {
  components: {
    TodoItem,
  },
  data() {
    return {
      todos: [
        { id: 1, text: "Belajar VueJS", done: false },
        { id: 2, text: "Membangun aplikasi to-do", done: false },
        { id: 3, text: "Minum kopi", done: true },
      ],
      newTodo: "",
<<<<<<< HEAD
      filter: "pending", // Setel filter default ke 'pending'
=======
      filter: "all",
>>>>>>> a366d0e045f979b231dc5fd9f74ce7443c87f120
    };
  },
  computed: {
    filteredTodos() {
      if (this.filter === "all") {
        return this.todos;
      } else {
        return this.todos.filter((todo) => !todo.done);
      }
    },
  },
  methods: {
    addTodo() {
      if (this.newTodo.trim()) {
        this.todos.push({ id: Date.now(), text: this.newTodo, done: false });
        this.newTodo = "";
      }
    },
    toggleDone(index) {
      this.todos[index].done = !this.todos[index].done;
    },
    deleteTodo(index) {
      this.todos.splice(index, 1);
    },
<<<<<<< HEAD
    editTodo(index, newText) {
      if (newText.trim()) {
        this.todos[index].text = newText;
      }
    },
=======
>>>>>>> a366d0e045f979b231dc5fd9f74ce7443c87f120
  },
};
</script>

<style scoped>
.todo-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.todo-list li {
  display: flex;
  align-items: center;
  padding: 10px;
  border-bottom: 1px solid #ccc;
}

.todo-list .completed {
  text-decoration: line-through;
  color: #aaa;
}

.filter-container {
  display: flex;
  margin-bottom: 10px;
}

<<<<<<< HEAD
.filter-container button {
  margin-right: 10px;
  padding: 5px 10px;
  border: none;
  background-color: #f0f0f0;
  cursor: pointer;
}

.filter-container .active {
  background-color: #ccc;
=======
.filter-container label {
  margin-right: 10px;
>>>>>>> a366d0e045f979b231dc5fd9f74ce7443c87f120
}
</style>
