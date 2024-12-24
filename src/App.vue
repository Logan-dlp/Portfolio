<script>
     import './assets/App.css'

     import Home from './components/Home.vue'
     import About from './components/About.vue'
     import NotFound from './components/NotFound.vue'

     const routes = {
       '/': Home,
       '/about': About
     }

     export default {
          data() {
               return {
               currentPath : window.location.hash
          }
          },
          computed: {
               currentView() {
                return routes[this.currentPath.slice(1) || '/'] || NotFound
               }
          },
          mounted() {
               window.addEventListener('hashchange', () => {
               this.currentPath = window.location.hash
               })
          },
     }
</script>

<template>
     <nav class="navbar">
          <a href="#/"><img src="../public/logo.svg" alt="" class="logo"> portfolio - delachapelle logan</a>
          <ul class="nav-links">
               <li><a href="#/about">about</a></li>
               <li><a href="#/projects">projects</a></li>
               <li><a href="#/contact">contact</a></li>
          </ul>
     </nav>

     <Transition name="fade" mode="out-in">
          <component :is="currentView"/>
     </Transition>

</template>

<style scoped>

.fade-enter-active {
     transition: all 0.3s ease-out;
}

.fade-leave-active {
     transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}

.fade-enter-from,
.fade-leave-to {
     transform: translateY(20px);
     opacity: 0;
}

</style>