<script>
     import Home from './components/Home.vue'
     import About from './components/About.vue'
     import Skill from './components/Skill.vue'
     import Contact from './components/Contact.vue'
     import NotFound from './components/NotFound.vue'
     import Navbar from './components/Nav.vue'

     const routes = {
       '/': Home,
       '/about': About,
       '/skill': Skill,
       '/contact' : Contact,
     }

     export default {
          components: {
               Navbar,
          },

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
     <Navbar />

     <Transition name="fade" mode="out-in" class="comp">
          <component :is="currentView" />
     </Transition>
     
</template>

<style scoped>

.comp {
     margin: 0;
}

.fade-enter-active {
     transition: all 0.5s ease-out;
}

.fade-leave-active {
     transition: all 0.5s cubic-bezier(1, 0.5, 0.8, 1);
}

.fade-enter-from,
.fade-leave-to {
     transform: translateY(20px);
     opacity: 0;
}

</style>