<template>
     <h1 class="text-center pt-3">Welcome</h1>
  <div class="container">
    <div class="row justify-content-center align-items-center">
      <div class="col-md-6">
        <div class="box">
          <router-link to="/signin-user"> Signin </router-link> 
        </div>
      </div>
      <div class="col-md-6">
        <div class="box">
          <router-link to="/signup-user"> Signup </router-link> 
        </div>
      </div>
    </div>
  </div>
   <!-- Starting point for the components -->
    <router-view></router-view>
</template>

<script>


export default {
  /*  components: { 
    LoginForm ,
    SignupForm
  }, */
};
</script>

<style scoped>
.box {
 color: #333;
  margin:30px 0px;
}
.row .col-md-6:first-child .box{
 text-align: right;
}
</style>