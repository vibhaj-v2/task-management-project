<template>
  <div class="container">
    <div class="row">
      <div class="col-md-12">
        <div
          class="form-container d-flex justify-content-center align-items-center">
           <form @submit.prevent="onSubmit()">
            <div class="form-group">
              <input
                type="text"
                class="form-control mb-3"
                id="userName"
                name="userName"
                  v-model="userName"
                placeholder="Enter Username"/>
              
               <p v-if="!isValidUname" style="color: red">
              Please enter the valid username !!!
            </p>
            </div>
            <div class="form-group">
              <input
                type="password"
                class="form-control"
                id="password"
                name="password"
                 v-model="password"
                placeholder="Enter Password"/>
               
               <p v-if="!isValidPassword" style="color: red">
              Please enter the valid password !!!
            </p>
            </div>
            <button type="submit" class="form-control mt-3 btn btn-primary">Submit</button>
          </form>
        </div>
      </div>
    </div>
  </div>
  <router-view></router-view>
</template>

<script>
export default {
  data() {
    return {
      userName: "",
      password:"",
      isValidUname: true,
      isValidPassword: true
    };
  },
  methods: {
    onSubmit1() {
      console.log("userName ", this.firstName);
      console.log("userName ", this.lastName);
    },
    
    onSubmit() {
      this.isValidName = true;
       this.isValidPassword = true;
      if (this.userName === "") {
        this.isValidUname = false;
               
        }
      if (this.password === "") {
        this.isValidPassword = false;
      }
     else{this.$router.push("/dashboard");} 
     
    },
  },
};
</script>
<style>
.form-container {
  max-width: 100%;
  height: 50vh;
}
form {
  max-width: 400px;
  background-color: #ddd;
  padding: 20px;
}
.invalidEntry {
  color: red;
}
</style>
