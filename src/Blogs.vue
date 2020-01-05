<template>
    <div>
        <h2>{{ blogTitle }}</h2>
        
         Search: <input class="search" type="text" v-model="searchTerm"><br><br>
         <button @click="changeTitle">Change Title</button>

          
        <div v-for="post in filteredPosts" :key="post.id">
            <h3 class="title">{{ post.title}}</h3>
            <p>{{ post.body | snippet}}...</p>
          </div>

       
    </div>
</template>

<script>
import  axios  from 'axios';
export default {
    name: 'Blogs',
    data(){
        return{
            blogTitle : 'Latest Blog Posts',
            posts: [],
            searchTerm: ''
        }
    },
    methods:{
        changeTitle(){
            this.blogTitle = 'Recent Blog Posts'
        }
    },
     computed:{
        filteredPosts(){
            return this.posts.filter(post =>{
                return post.title.match(this.searchTerm)
            })
        }
    },
    beforeCreate(){
        //alert('before Create Hook');
    },
    created(){
        //alert('created hook')
        axios.get('https://jsonplaceholder.typicode.com/posts/?userId=1')
        .then( response => {
            //console.log(response);
            this.posts = response.data;
        }).catch(err =>{
            console.log(err);
        })
    },
    beforeUpdate(){
       //  alert('before update hook')
    }
}
</script>

<style>
.title{
    text-transform: capitalize;
}
</style>