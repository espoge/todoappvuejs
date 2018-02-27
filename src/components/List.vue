<template>

<div>

<div class="cnt-checkbox">
  <input type="checkbox" v-model="showcompleted" id="comp"><label for="comp" v-bind:class="[showcompleted ? 'active' : 'inactive']">Completed</label>
  <input type="checkbox" v-model="showincompleted" id="incomp"><label for="incomp" v-bind:class="[showincompleted ? 'active' : 'inactive']">Incomplete</label>
</div>
<div class="cnt-list-task">
  <div v-if="showcompleted">
    <h2>Completed {{completedTask.length}}</h2>
    <p v-if="completedTask.length===0">You have completed all tasks</p>
    <singleTask v-for='task in completedTask' :task='task' v-on:deleteTask="deleteTask"></singleTask>
  </div>
  <div v-if="showincompleted">
    <h2>Incomplete {{incompletedTask.length}}</h2>
    <p v-if="incompletedTask.length===0">Any incompleted task to show</p>
    <singleTask v-for='task in incompletedTask' :task='task' v-on:doneTask="doneTask"></singleTask>
  </div>

</div>
  </div>
</template>
<script>
  import SingleTask from './SingleTask.vue'
  export default {
    data:function(){
      return {
        showcompleted: true,
        showincompleted: false,
      }
    },
    props: ['tasks'],
    components: {
      'singleTask': SingleTask
    },
    methods:{
      deleteTask(task){
          const indexTask=this.tasks.indexOf(task);
          this.tasks.splice(indexTask, 1);
      },
      doneTask(task){
          const indexTask=this.tasks.indexOf(task);
          this.tasks[indexTask].completed = true;
      }
    },
    computed: {
       incompletedTask(){
        return this.tasks.filter(task => !task.completed);
      },

      completedTask(){
        return this.tasks.filter(task => task.completed);
      },
    }

  }
</script>
<style>
input[type="checkbox"] {
  display:none;
}
input[type="checkbox"] + label {
  cursor: pointer;
  padding: 10px;
  border-radius: 4px;
}
p {color:#4EA65B; font-size: 18px;}
h2 {color: #636363}
.active {
  background-color: #0c0;
  color: #f4f4f4
}
.inactive {
  background-color: #c1c1c1;
  color:#919191;
}
.cnt-checkbox {
  width: 200px;
  display: block;
  margin: 20px auto;
}
.cnt-list-task {
  display: flex;
	display: -webkit-flex;
	-webkit-flex-direction: row;
	flex-direction: row;
	align-items: flex-start;
	-webkit-align-items: flex-start;
	justify-content:center;
	 -webkit-justify-content: center;
}
.cnt-list-task > div {width: 30%}
.flex-list div:nth-child(2) {
  width: 150px;
}
</style>
