<template>
    <div class="hello">
      <h2>This is {{title}} page and user id ({{userID}})</h2>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Profile',
    data () {
      return {
          title:'Profile',
          userID : this.$route.params.user_id
      }
    },
    methods:{
      updateId(){
        this.userID = this.$route.params.user_id
      }
    },
    watch:{
      $route: 'updateId'
    }
  }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped>
  h2{
    color: green;
  }
  </style>
  