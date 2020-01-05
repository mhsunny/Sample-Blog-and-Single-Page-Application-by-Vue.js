<template>
  <div id="app">
   <h1>{{title}}</h1>
     
   <Navbar />

  <div class="functional" >
    
  
    <div class="left">
<ul>
     <li>Nesting Component</li>
     <li>Comunicating between components via parent component</li>
     <li>Scoped Css</li>
     <li>Passing Data with Props</li>
     <li>Custom Events</li>
     <li>Life-cycle Hooks</li>
     <li>Making JSON api Requests with Axios / Ajax Request</li>
    <li>Filter</li>
    <li> Computed Properties (custom search box)
</li>
   </ul>
      </div>
         <p>Click of each item, then it will removed from the list</p> 
   <div class="left"> 
      <AllFriends :friends="friends" @delete="deleteFriend"/>
   </div>
    <div class="left">
      <OnlineFriends  :friends="friends"/>
    
   </div>
   <div class="clearfix"></div>
   </div>



    <Blogs />
  
  
  </div>
</template>

<script>
import Navbar from "./Navbar";

import AllFriends from "./AllFriends";

import OnlineFriends from "./OnlineFriends";
import Blogs from "./Blogs";

export default {
  name: 'app',
  components:{
    Navbar,
    AllFriends,
    OnlineFriends,
    Blogs
  },
  data () {
    return {
      title: 'Single page and Sample Blog Site by Vue.js',
       friends:[

                {name: 'Sunny', online:true},
                {name: 'Kaniz', online:false},
                {name: 'Yellin', online:true},
                {name: 'Bros', online:false}
                
            ]
      
    }
  },
  methods:{
    deleteFriend(payload){
      console.log(payload);
      this.friends = this.friends.filter(friend => {
        return friend.name !== payload.name;
      })
    }
  }
}
</script>

<style scoped>
 ul li{
   text-align: left;
 }
body{
  background: aquamarine;
}
#app{
  text-align: center;
  width: 960px;
  max-width: 100%;
  margin: 0 auto;

}
.left{
  float:left;
  width: 33%;
}
.clearfix{
  clear: both;
}
h1{
  color:#444;
  text-align:center;
  font-weight:normal;
}
.functional{
  padding: 1rem;
  background: yellow;
}
 
</style>
