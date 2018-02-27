<template>
<div class="flex-list">
    <div>
      <svg version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
    width="20px" height="20px" viewBox="0 0 60 60" enable-background="new 0 0 10 10" xml:space="preserve">
      <circle v-bind:class="[task.important ? 'important' : 'not-important']" cx="25" cy="25" r="24.294"/>
    </svg>
    </div>
    <div>
        {{task.description}}
    </div>
    <div>
      <svg version="1.1" class="check" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
       width="20px" height="20px" viewBox="0 0 50 50" enable-background="new 0 0 50 50" xml:space="preserve"  v-if="!task.completed" @click="doneTask(task)">
      <g>
        <path d="M25.683,1.339C12.61,0.964,1.713,11.254,1.336,24.324c-0.008,0.228-0.01,0.46-0.01,0.688
          c0,13.078,10.602,23.675,23.675,23.675c13.075,0,23.673-10.598,23.673-23.675C48.678,12.2,38.487,1.708,25.683,1.339L25.683,1.339
          z M35.55,13.296l4.689,4.688L26.17,32.043l-4.689,4.689l-4.676-4.689L9.76,25.012l4.692-4.688l7.029,7.029L35.55,13.296z
           M35.55,13.296"/>
      </g>
    </svg>
    <svg version="1.1" class="trash" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
       width="20px" height="20px" viewBox="0 0 50 50" enable-background="new 0 0 50 50" xml:space="preserve" v-if="task.completed" @click="deleteTask(task)">
    <g>
      <path d="M11.296,46.755c0.053,1.274,1.102,2.28,2.377,2.28h22.215c1.275,0,2.324-1.006,2.377-2.28l1.588-33.49
        H9.709L11.296,46.755z M29.806,21.583c0-0.534,0.433-0.967,0.968-0.967h1.545c0.533,0,0.967,0.433,0.967,0.967v19.134
        c0,0.534-0.434,0.967-0.967,0.967h-1.545c-0.534,0-0.968-0.433-0.968-0.967V21.583z M23.042,21.583
        c0-0.534,0.433-0.967,0.966-0.967h1.547c0.533,0,0.966,0.433,0.966,0.967v19.134c0,0.534-0.434,0.967-0.966,0.967h-1.547
        c-0.533,0-0.966-0.433-0.966-0.967V21.583z M16.276,21.583c0-0.534,0.433-0.967,0.967-0.967h1.545c0.534,0,0.967,0.433,0.967,0.967
        v19.134c0,0.534-0.433,0.967-0.967,0.967h-1.545c-0.534,0-0.967-0.433-0.967-0.967V21.583z M16.276,21.583"/>
      <path d="M40.909,4.186H30.661V2.249c0-0.275-0.225-0.499-0.5-0.499H19.4c-0.275,0-0.499,0.223-0.499,0.499v1.937
        H8.653c-0.825,0-1.494,0.669-1.494,1.494v4.691h35.242V5.679C42.401,4.855,41.733,4.186,40.909,4.186L40.909,4.186z M40.909,4.186"
        />
    </g>
    </svg>
    </div>

</div>
</template>
<script type="text/javascript">
  export default {
    props: ['task'],
    methods: {
      doneTask(task){
        this.$emit('doneTask', task)
      },
      deleteTask(task){
        this.$emit('deleteTask', task)
      },
    }

  }

</script>
<style scope>
  svg {cursor:pointer;}
  .trash, .check {fill: #ccc}
  .trash:hover {fill: #E12D53}
  .check:hover {fill: #46B29D}
 .flex-list {display: flex;display: -webkit-flex; }

</style>
