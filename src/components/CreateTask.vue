<template>
  <div>
  <input type="text" v-model="description" placeholder="description" required>
  <select v-model="important">
  <option v-bind:value="true">important</option>
  <option v-bind:value="false">not important</option>
</select>
  <button @click="sendTask">Add Task</button>
  </div>
</template>
<script>
  export default {
    data(){
      return {
        description:'',
        important:'',
        completed: false
      }
    },
    methods: {
      sendTask() {
          const description = this.description;
          const important = this.important;
          const completed = this.completed;
          this.$emit('addTask', {
            description,
            important,
            completed
          });
          this.description ='';
          this.important = '';
      }
    }
  }
</script>
<style scoped>
  div {width: 400px; display: block;margin: 0 auto;}
  input[type="text"], select {padding: 10px}
  button {background-color: #4C8DCA; color: #fff; border: none; padding: 10px 5px; cursor: pointer; border-radius: 4px}
</style>
