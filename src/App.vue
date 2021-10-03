<template>
  <div id="app">
    <PropiedadesVue></PropiedadesVue>
  </div>
</template>

<script>
import NewComponente from './components/NewComponente.vue'
import HelloWord from './components/HelloWord.vue'
import NameClass from './components/NameClass.vue'
import CrudExample from './components/CrudExample.vue'
import PropiedadesVue from './components/PropiedadesVue.vue'
export default {
  components: { NewComponente, HelloWord, NameClass, CrudExample, PropiedadesVue },
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
