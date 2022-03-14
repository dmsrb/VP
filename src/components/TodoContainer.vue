<template>
  <div>
    <h1>Todo List</h1>
    <b-form-input v-model="text" placeholder="Todo"/>
    <b-button @click='addTodoList'>ADD</b-button>
    <div v-for="msg in TodoList">
      <TodoItem :msg="msg"/>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import TodoItem from '@/components/TodoItem.vue';

@Component({
  components: {
    TodoItem,
  },
})
export default class TodoContainer extends Vue {
  private text = ''
  private TodoList:Array<string> = [] 
  // TodoList.push()

  addTodoList() :void{
 this.TodoList.push(this.text)
 this.text = ''
  }
};
</script>
