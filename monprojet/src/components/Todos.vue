<template>
  <sections class="class todoapp">

    <header class="class header">

      <h1 >Todos list</h1>

      <input type="text" class="new-todo" placeholder="Ajouter un champ" v-model="newTodo" @keyup.enter="addTodo">

    </header>

    <div class="main">

      <ul class="todo-list">

        <li class="todo" v-for="todo in todos" :class="{completed: todo.completed}">

          <div class="view">
<input type="checkbox" v-model="todo.completed">
            <label>{{todo.name}}</label>
          </div>

        </li>

      </ul>

    </div>
  </sections>

</template>

<script>

  export default {
    data(){
      return {
        todos:[{
          name: 'Tache de test',
          completed:false
        }],
        newTodo :'',

      }

    },
    methods:{
      addTodo(){
        this.todos.push({
          completed:false,
          name:this.newTodo
        })
        this.newTodo= ''
      }
    }
  }

  
</script>