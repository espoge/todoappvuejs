<template>
  <div class="main-cnt">
  <top :tasks='tasks'></top>
  <create-task  v-on:addTask="addTask"></create-task>
  <list :tasks='tasks'></list>
  <footerMore></footerMore>
  </div>
</template>

<script>
import List from './components/List.vue'
import Top from './components/Top.vue'
import CreateTask from './components/CreateTask.vue'
import Footer from './components/Footer.vue'
export default {
  data:function(){
    return {
    title: 'Todo List App',
    tasks: [
        {description:'Jogging',  important: true, completed: true},
        {description:'Homeworks', important: true, completed: false},
        {description:'Call to Marta', important: false, completed: false},
        {description:'Shopping', important: true, completed: true},
        {description:'Go to gym',  important: false, completed: true},
        {description:'Watch a movie', important: false, completed: false}
      ],

    }

  },
  components: {
    'list': List,
    'create-task': CreateTask,
    'top': Top,
    'footerMore': Footer
  },
  methods: {
    addTask(newTask){
      this.tasks.push(newTask);
    }
  }

}
</script>

<style>
  .main-cnt {
    width: 900px;
    display: block;
    margin: 0 auto;
    background-color:#D6F0F0;
    padding: 20px 0;

  }

  ul {list-style: none}
  li {display: inline; vertical-align: top;}
    .important {
      fill: #DB381B;
    }
    .not-important {
      fill: #F3A346;
    }
</style>
