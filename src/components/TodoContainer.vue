<template>
  <div>
    <b-button @click="addToDo">
      추가
    </b-button>
    <b-form-input
      v-model="text"
      placeholder="Enter Todo"
      @keydown
    />
    <div class="mt-2">
      Value: {{ text }}
    </div>
    <h1>TodoContainer</h1>
    <TodoItem
      v-for="msg in todoList"
      :key="msg"
      :msg="msg"
    />
    <TodoItem :msg="msg" />
    </b-button@click>
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
  private inputMsg = ''

  addToDo():void {
    this.todoList.push();
  }
}
</script>
