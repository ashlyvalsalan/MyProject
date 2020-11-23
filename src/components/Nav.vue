<template>
    <b-navbar class="b-nav">
        <b-navbar-brand class="b-nav-brand">             
               <h1>Explore the User Posts</h1>
        </b-navbar-brand>
    </b-navbar>  
</template>
<script>
    export default {
        name:'Nav'
    }
</script>
<style>
    .b-nav{
        overflow: hidden;
        background-color: #333;
        position: fixed;
        top: 0;
        width: 100%;
    }

    h1{
        position: center;
        color: plum;
   }
    .b-nav-brand{
        display: inline ;
        width: 100%;
    }
</style>