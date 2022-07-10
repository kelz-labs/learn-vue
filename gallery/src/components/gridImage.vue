<template>
  <h1 class="text-center font-bold text-4xl">Gallery Vue</h1>
  <div class="flex flex-col mt-4 justify-center items-center">
    <div class="grid grid-cols-3 grid-rows-3">
      <div class="flex rounded-tl-full overflow-hidden">
        <img src="https://source.unsplash.com/random" width="250px" height="250px"/>
      </div>
      <div class="flex overflow-hidden">
        <img src="https://source.unsplash.com/random" width="250px" height="250px"/>
      </div>
      <div class="flex rounded-tr-full overflow-hidden">
        <img src="https://source.unsplash.com/random" width="250px" height="250px"/>
      </div>
      <div class="flex rounded-bl-lg overflow-hidden">
        <img src="https://source.unsplash.com/random" width="250px" height="250px"/>
      </div>
      <div class="flex overflow-hidden">
        <img src="https://source.unsplash.com/random" width="250px" height="250px"/>
      </div>
      <div class="flex rounded-br-lg overflow-hidden">
        <img src="https://source.unsplash.com/random" width="250px" height="250px"/>
      </div>
    </div>
  </div>

  <ul class="list-none text-2xl font-bold flex justify-center items-center">
    <a href="/" class="px-4 py-2">Home</a>
    <a href="/anime" class="px-4 py-2">Anime</a>
    <a href="/contact" class="px-4 py-2">Contact</a>
  </ul> 
</template>

<script>
  import Home from "../home.vue"
  import Anime from "../anime.vue"
  import Contact from "../contact.vue"
  import VueRouter from "vue-router"; 
  import Vue from "vue"; 

  // contoh router di vuejs pakai vue-router 
  const routes = [
    { path: '/', component: Home, },
    { path: '/anime', component: Anime, },
    { path: 'contact', component: Contact, },
  ]

  const router = VueRouter.createRouter({
    history: VueRouter.createWebHashHistory(), 
    routes, 
  })

  const app = Vue.createApp({})
  app.use(router)

  app.mount('#app')

  export default {
  computed: {
    username() {
      // We will see what `params` is shortly
      return this.$route.params.username
    },
  },
  methods: {
    goToDashboard() {
      if (isAuthentificated) {
        this.$router.push('/dashboard')
      } else {
        this.$router.push('/login')
      }
    },
  },
}

</script>
