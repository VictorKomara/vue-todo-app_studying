<script setup>
  import todos from './data/todos';

  const addTodo = async () => {
    if (!title.value) return;

    const newTodo = await todoApi.createTodo(title.value);

    todos.value.push(newTodo);
    title.value = '';
  };

</script>

<template>
  <nav class="filter">
  <a
    href="#/"
    class="filter__link"
    :class="{ selected: status === 'all' }"
    @click="status = 'all'"
  >
    All
  </a>
  <a
    href="#/active"
    class="filter__link"
    :class="{ selected: status === 'active' }"
    @click="status = 'active'"
  >
    Active
  </a>
  <a
    href="#/completed"
    class="filter__link"
    :class="{ selected: status === 'completed' }"
    @click="status = 'completed'"
  >
    Completed
  </a>
</nav>

</template>
