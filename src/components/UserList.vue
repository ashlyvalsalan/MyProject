<template class="temp-userList">
    <b-container class="b-contain">
        <b-row class="b-row">
            <b-col cols="6" class="b-column" v-for=" user of users" :key="user.id">
                <b-card>
                    <a  v-on:click="retrievePosts(user.id)">{{user.name}}</a>
                </b-card>
            </b-col>  
        </b-row>
        <b-row class="b-row">       
             <b-col cols="6" class="b-post-column" v-for=" post of posts" :key="post.id">
                <b-card>
                    <a  v-on:click="retrieveDetail(post.id)" >{{post.title}}</a>
                </b-card>
            </b-col>    
        </b-row>
        <b-row class="b-row">
             <b-col cols="12" class="b-detail-column" v-for=" det of detail" :key="det.id">
                 <b-card>
                <a >{{det.body}}</a>  
                 </b-card>
            </b-col>          
        </b-row>
    </b-container>  
</template>
<script>
import axios from 'axios';
export default {
  name: 'UserList',
  data(){
      return {
          users: [],
          posts: [],
          detail:[],
      };
  },
  async created(){
      try{
          const res= await axios.get(`https://jsonplaceholder.typicode.com/users`);
          this.users= res.data;
        }
      catch(e){
         console.error(e); 
      }
  },
  methods:{ 
      retrievePosts(id)
      {
       
        axios.get("https://jsonplaceholder.typicode.com/posts?userId="+id)
        .then(response=>{
        this.posts=response.data;
        })  
        this.retrieveDetail(0);
    
      },
      retrieveDetail(postId)
      {
          
        axios.get("https://jsonplaceholder.typicode.com/posts?id="+postId)
        .then(response=>{
        this.detail=response.data;
     
        })
    },
   }
};
</script>
<style> 
.temp-userList
{
    background-color: hotpink;
}
.b-column
{
    height: 100%;
    background-color:cornsilk;
    padding: 35px;
    color: brown;
    font-weight: bold;
    top: 40px;
}
.b-row{
    padding:35px;
    width: 100%;
}
.b-post-column{
    
    background-color:rgb(220, 255, 240);
    padding: 20px;
    color: rebeccapurple;
    font-weight:normal;
    top: 55px;

}
.b-detail-column{
    background-color:plum;
    padding: 10px;
    color: seagreen;
    font-weight: lighter;
    top: 55px;
}
</style>

