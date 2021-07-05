<template>
    <div class="todo-item" :class="{'is-complete' : todo.completed}">
       <p>
           <input type="checkbox" v-on:change="markComplete">
           {{todo.title}}</p>
           <button @click="$emit('del-todo',todo.id)" class="del">X</button>
    </div>
</template>

<script>
export default {
    name:"TodoItem",
    props:["todo"],
    methods:{
        markComplete() {
            this.todoLocal.completed=!this.todoLocal.completed;
        }
    },
    data()
    {
       return{
           todoLocal:this.todo,
       };
    }
    
}
</script>



<style scoped>
.todo-item
  {
      background: #f4f4f4;
      padding: 10px;
      border-bottom: 1px #ccc dotted;
  }
  .del
  {
      background: #ff0000;
      color: #fff;
      border: none;
      padding: 5px 9px;
      border-radius: 50%;
      cursor: pointer;
      float:right;
  }
  .is-complete
  {
      text-decoration: line-through;
  }
</style>