<template>
    <div id="nav" class="h-12">
        <!-- nav to: using path -->
        <router-link to="/home">Home</router-link> 
        <router-link to="/about">About</router-link> 

        <!-- nav to: using name -->
        <!-- <router-link :to="{ name: 'HomePage' }">Home</router-link> |
        <router-link :to="{ name: 'AboutPage' }">About</router-link> -->
    </div>
</template>

<script>
import { mapActions } from 'vuex'

export default {
    name: 'NavComponent',
    methods: {
        ...mapActions('auth', {
            logoutUser: 'logout'
        }),
    }
}
</script>