<template>
   <div class="container">
<div class="row">
<div class="col-md-12">
    <h1 class="main-heading">Welcome to Task Management</h1>
</div>
<div class="col-md-12">
<nav>
<div class="left-link">
<ul>
        <li>Dashboard</li>
        <li>Createtask</li>
        <li>Tasklist</li>
        <li>Taskstatus</li>
        </ul>
    </div>
    <div class="right-link">
        <ul class="navbar-nav ml-auto">
        <li>Logout</li>
        </ul>
    </div>

</nav><!--nav closed -->

</div>
</div><!--row closed -->
<div class="row">
    <div class="box-container d-flex justify-content-center align-items-center text-center text-white">
<div class="col-md-6">
                    <div class="box">
                         <router-link to="/create-task"> Create Task </router-link> 
                    </div>
                    
                </div>
                <div class="col-md-6">
                    <div class="box">
                         <router-link to="/list-task"> List task </router-link> 
                    </div>
                </div>
                </div>
</div><!--2nd row closed -->

   </div><!--container closed -->
    <!-- Starting point for the components -->
    <router-view></router-view>
</template>
<style scoped>
.main-heading{text-align: center; padding: 20px 0px;}
nav{
    display: flex;
    justify-content: space-between;
    background: #eee;
    padding: 10px;
}
nav ul {display:flex; list-style: none; justify-content :start; align-items: center;}
nav ul li{display: inline-block; padding: 0px 5px; font-weight: bold;;}

.box{max-width: 200px; background-color: #333; margin: 40px auto;}
</style>