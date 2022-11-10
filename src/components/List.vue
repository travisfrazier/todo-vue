<template>
  <section class="container">
    <Form v-on:added="addToDo" />
    <ul>
      <draggable v-model="ToDoItems">
      <li v-for="item, index in ToDoItems" :key="item.id">
        <Item
          :done="item.done"
          :key="item.id"
          :label="item.label"
          :id="item.id"
          @markItemComplete="markComplete(index)"
          @deleteItem="deleteToDo(index)"
        />
      </li>
      </draggable>
    </ul>
    <div class="list-functions">
      <span @click="clearCompleted">Clear Completed</span>
    </div>
  </section>
</template>

<script>
import Item from "./Item.vue";
import Form from "./Form";
import uniqueId from "lodash.uniqueid";

import draggable from 'vuedraggable'

export default {
  data() {
    return {
      ToDoItems: [],
    };
  },
  components: {
    Item,
    Form,
    draggable
  },
  methods: {
    addToDo(toDoLabel) {
        this.ToDoItems.push({id:uniqueId('todo-'), 
        label: toDoLabel, 
        done: false
      });
    },
    deleteToDo(index) {
      this.ToDoItems.splice(index, 1);
    },
    clearCompleted() {
      const newList = this.ToDoItems.filter(item => {
        return item.done != true;
      })
      this.ToDoItems = newList;
    },
    markComplete(index) {
      this.ToDoItems[index].done = !this.ToDoItems[index].done
    }
  },
};
</script>

<style lang="scss" scoped>
</style>