<template>
 
 <router-view></router-view>
</template>

<script>


export default {

  data(){

    return {tasksArray:[]}

  },
  methods: {
   addValues (task){
this.tasksArray.push(task);
   }
  },
  provide(){
    return {tasks:this.tasksArray, addValues: this.addValues}
  }

  /*  components: { 
    LoginForm ,
    SignupForm
  }, */
};
</script>
<style>
* { margin: 0; padding: 0; }
</style>
