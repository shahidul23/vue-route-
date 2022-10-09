<template>
    <div id="app">
        <nav>
            <ul>
                <!-- <li><a href="">Home</a></li>
                <li><a href="">About</a></li>
                <li><a href="">Contact</a></li> -->
                <li><router-link to="/">Home</router-link></li>
                <li><router-link to="/about">About</router-link></li>
                <li><router-link :to="{name:'contact'}">Contact</router-link></li>
            </ul>
        </nav>
        <div>
            <ul v-for="(id,index) in userId" :key="index">
                <li><router-link :to="{ name : 'profile',params:{user_id:id} }">Profile {{id}}</router-link></li>
            </ul>
            <button @click="About">About</button>
            <button @click="Contact">Contact</button>
            <button @click="Back">Back</button>
            <button @click="Forward">Forward</button>
        </div>
    </div>
</template>

<script>
export default {
    name:'Navbar',
    data(){
        return {
          userId :['1','2','3','4','5','7','10']
        }
    },
    methods:{
    About(){
         this.$router.push( {name: 'about'} )
    },
    Contact(){
        this.$router.push({name:'contact'})
    },
    Back(){
        this.$router.go(-1)
    },
    Forward(){
        this.$router.go(1)
    }
}
}
</script>

<style scoped>
   nav {
    text-align: center;
   }
   nav ul {
    padding: 0;
   }
   nav li{
    display: inline-block;
    list-style-type: none;
    margin: 0;
    padding: 8px;
   }
   a.router-link-exact-active{
    color: green;
   }
</style>
