<template>
  <div class="container">
    <InputField
    v-model="newTask"
    placeholder="Enter a new task"
    @keydown.enter="addTask"
    />
    <ul>
      <TaskItem
      v-for="todo in todos"
      :key= "todo.id"
      :todo= "todo"
      @remove="removeTask"
      />
    </ul>
     
  </div>
</template>

<script>
import TaskItem from './TaskItem.vue';
import InputField from './InputField.vue';

let newTaskId = 1;

export default {
  components: {
    InputField, TaskItem
  },
  data () {
    return {
      newTask: '',
      todos: [
        {id: newTaskId++, text:'Learn Vue Fundamentals'}, 
        {id: newTaskId++, text:'Practice Vue'},
        {id: newTaskId++, text:'Build a silly product to practice'}
      ]
    }
  },
  methods: {
   addTask () {
     const trimTask = this.newTask.trim();
     if(trimTask) {
       this.todos.push({
         id: newTaskId++,
         text: trimTask
       })
        this.newTask = '';
       }
     },
     removeTask(taskDeleteId) {
       this.todos = this.todos.filter(todo => {
         return todo.id !== taskDeleteId
       })
     }   
   }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url("https://fonts.googleapis.com/css?family=Montserrat");
body {
  font-family: "Montserrat", sans-serif;
  font-size: 24px;
  display: flex;
  justify-content: center;
}
small {
  font-size: 0.8em;
  color: #666;
  font-style: italic;
}
table {
  width: 100%;
  border-spacing: 0;
}
td {
  padding: 0.25em;
}
table > thead > tr > td {
  border-bottom: 1px solid #666;
}
table > tbody > tr:nth-child(even) {
  background: #eee;
}
input,
button {
  font-size: inherit;
  font-family: inherit;
}
form {
  display: flex;
}
form > input[type="text"] {
  flex-grow: 1;
  margin-right: 0.5em;
}

.valid small {
  color: forestgreen;
  font-weight: bold;
}

.valid input {
  border: 1px solid forestgreen;
}

.error small {
  color: #ff4136;
  font-weight: bold;
}

.error input {
  border: 1px solid #ff4136;
}
</style>
