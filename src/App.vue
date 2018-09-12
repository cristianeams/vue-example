<template>
  <div id="app">
    <h1>todoLIST</h1>
    <TasksContainer/>
  </div>
</template>

<script>
import TasksContainer from "./components/TasksContainer.vue";

export default {
  name: "app",
  components: {
    TasksContainer
  }
};
</script>

<style>

@import url('https://fonts.googleapis.com/css?family=Mukta');
body {
  background-color: rgb(67, 204, 158);
}
#app {
  font-family: "Mukta", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: lightslategrey;
  margin-top: 60px;
}
h1 {
  text-align: center;
  color: whitesmoke;
}
input {
  border-radius: 8px;
  width: 40%;
  padding: .6em;
  margin-bottom: 1em;
  border: 2px solid rgb(67, 204, 158);
}
ul {
  margin: auto;

  border-radius: 8px;
  background-color: white;
  width: 38%;
}
li {
  padding: 1em;
  list-style-type: none;
  display: flex;
  flex-direction: row nowrap;
  justify-content: space-between;
  border-bottom: 1px solid lightseagreen;
}
button {
  background-color: rgb(67, 204, 158);
  color: white;
  font-size: .8em;
  border-radius: 8px;
  width: 15%;
  padding: .3em .5em;
  transition: all .5s;
}
button:hover {
   background-color: rgb(232, 83, 90);
   font-weight: bold;
}
</style>
