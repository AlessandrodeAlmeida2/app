<template>
  <TheHeader />
  <div v-for="obj in todos" v-bind:key="obj.id" class="todosItem">
    {{ obj.title }}
  </div><br>
  <h2>Todos em aberto</h2>
  <div v-for="todo in uncompleted" :key="todo.id" class="todosItem">
    {{ todo.title }}
  </div><br>
  <h2>Todos completos</h2>
  <div v-for="todo in completed" :key="todo.id" class="todosItem">
    {{ todo.title }}
  </div><br>
  <teste />
  <BaseCard 
  v-if="showAlert" 
  :variant="variant" 
  v-on:close="onClose()">
    {{ text }}
  </BaseCard>
</template>

<script>
import BaseCard from './components/BaseCard.vue';
import TheHeader from './components/TheHeader';
import teste from './components/teste';

export default {
  name: 'App',
  components: {
    TheHeader,
    teste,
    BaseCard
},
  data() {
    return {
      todos: [
        {
            "userId": 1,
            "id": 1,
            "title": "delectus aut autem",
            "completed": false
        },
        {
            "userId": 1,
            "id": 2,
            "title": "quis ut nam facilis et officia qui",
            "completed": false
        },
        {
            "userId": 1,
            "id": 3,
            "title": "fugiat veniam minus",
            "completed": false
        },
        {
            "userId": 1,
            "id": 4,
            "title": "et porro tempora",
            "completed": true
        },
        {
            "userId": 1,
            "id": 5,
            "title": "laboriosam mollitia et enim quasi adipisci quia provident illum",
            "completed": false
        }
      ],
      showAlert: true,
      variant: 'success',
      text: 'Seu formulário foi enviado'
    }
  },
  computed: {
    uncompleted() {
      return this.todos.filter(todo => !todo.completed);
    },
    completed() {
      return this.todos.filter(todo => todo.completed)
    }
  },
  methods: {
    onClose() {
      this.showAlert = false;
      console.log('on close');
    }
  }
}

</script>

<style>
.todosItem {
  background: #000;
  color: blanchedalmond;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
