<template>
<div>
  <h1>{{title}}</h1>
<h2>Total task {{tasks.length}}</h2>
<ul>
<li>type your task and set its priority:</li>
<li><svg version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
width="20px" height="20px" viewBox="0 0 60 60" enable-background="new 0 0 10 10" xml:space="preserve">
<circle class="important" cx="25" cy="25" r="24.294"/>
</svg></li>
<li>important</li>
<li><svg version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
width="20px" height="20px" viewBox="0 0 60 60" enable-background="new 0 0 10 10" xml:space="preserve">
<circle class="not-important" cx="25" cy="25" r="24.294"/>
</svg></li>
<li>not important</li>
</ul>
</div>
</template>

<script type="text/javascript">
  export default {
    props: ['tasks'],
    data:function () {
      return {
        title: 'Todo List App'
      }
    }

  }

</script>

<style scoped>
  h1, h2{text-align: center;}
  h1 {color: #009AA7}
  h2 {color: #FF5349}
  ul {width: 425px; display: block; margin: 0 auto;}
</style>
