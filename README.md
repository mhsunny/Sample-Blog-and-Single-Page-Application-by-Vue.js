# Sample-Blog-and-Single-Page-Application-by-Vue.js

> Sample-Blog-and-Single-Page-Application-by-Vue

<h3>I try to cover the following basic of vue js</h3>
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
## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
```
<code>  
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
  </code>
For detailed explanation on how things work, consult the [docs for vue-loader](http://vuejs.github.io/vue-loader).
"# Sample-Blog-By-Vue.js" 
