<template>
  <div class="todo-item">
    <div class="left-side">
      <input class="checkbox" type="checkbox" />
      <div>
        <h3 class="title">Walk the dog</h3>
        <p class="description">Go around the block twice</p>
      </div>
    </div>

    <button class="action">Action</button>
  </div>
</template>

<style scoped>
h1 {
  font-size: 1.5rem;
}
.todo-item {
  display: flex;
  justify-content: space-between;
  box-shadow: 0px 0px 2px 2px rgba(0, 0, 0, 0.1);
  border-radius: 5px;
  padding: 10px;
  margin-bottom: 15px;
}
.left-side {
  display: flex;
}
.checkbox {
  display: block;
  transform: scale(2);
}
.title,
.description {
  margin: 0;
  padding: 0 10px 0 10px;
}
.title {
  margin-bottom: 0;
}
</style>
