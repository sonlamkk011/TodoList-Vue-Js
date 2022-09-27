<template>
  <div id="app">
    <div >
      <h1 class="title">TODO LIST</h1>
      <input class="input" type="text" v-model="newTask" />
      <button :class="{ add: addtask }" @click="addtask()">Thêm todo</button>
      <div v-for="(task, index) in tasks" :key="index">
        <input type="checkbox" v-model="task.done" />
        <span :class="{ done: task.done }">{{ task.content }}</span>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: "App",
  data() {
    return {
      newTask: "",
      tasks: [],
    };
  },
  methods: {
    addtask: function () {
      this.tasks.push({
        content: this.newTask,
        done: false,
      });
    },
  },
};
</script>

<style>
.title{
  color: blueviolet;
}

.input {
  border-radius: 10px;
  border-color: aquamarine;

}

.done {
  text-decoration: line-through;
  color: darkgray;
}
.add {
  background-color: yellowgreen;
  border-color: aquamarine;
  border-radius: 30px;
  margin-left: 10px;
}
.container {
  text-align: center;
}
</style>





