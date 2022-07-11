<template>
    <div class="navbar">
       <h1>My Vuex App Todos</h1>
       <ul>
           <li>Home</li>
           <li>About</li>
           <li v-if="isAuthenticated">
               Todal todos: {{ todos.length }}
               <button @click="TOGGLE_AUTH"> logout </button>
            </li>
            <button @click="TOGGLE_AUTH" v-else>
                Login
            </button>
       </ul>
    </div>
</template>

<script>
import  { mapMutations, mapGetters } from 'vuex'
    export default {
       name: 'Navbar',
       computed: mapGetters(['todos','isAuthenticated']),
       methods: mapMutations(['TOGGLE_AUTH'])
    }
</script>

<style scoped>
.navbar {
 padding: 5px;
 text-align: center;
 background: rgb(240, 240, 240);
 color: black;
}

.navbar ul {
 display: flex;
 justify-content: space-around;
 align-items: center;
 list-style: none;
 padding: 0;
}
</style>