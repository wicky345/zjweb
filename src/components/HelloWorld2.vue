<template>
  <div class="users">
  	<h1>users</h1>
    <!-- 添加用户信息 -->
    <form v-on:submit="addUser">
      <input type="text" v-model="newUser.name" placeholder="enter name">
      <input type="text" v-model="newUser.email" placeholder="enter email">
      <input type="submit" value="submit">
    </form>

    <!-- 展示用户信息 -->
    <ul>
      <li v-for="user in users" :key="user.name">
        <!-- <input type="checkbox" class="toggle" v-model="user.contacted"> -->
         {{user.name}}:{{user.email}}
          <button v-on:click="deleteUser(user)">x</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'users',
  data () {
    return {
    	users:[
        {name:'henry',email:'henry.com',contacted:false},
        {name:'wu',email:'wu.com',contacted:false},
        {name:'wei',email:'wei.com',contacted:false}
      ],
      newUser:{}
    }
  },
  methods:{
  	addUser:function(e){
      e.preventDefault();
      this.users.push({
        name:this.newUser.name,
        email:this.newUser.email,
        contacted:false
      });
    },
    deleteUser:function(user){
      this.users.splice(this.users.indexOf(user),1);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>