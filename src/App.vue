<template>
  <div id="nav">
    
    <router-link to="/">Home</router-link> |
    <router-link to="/registro">Registrarse</router-link> |

    <router-link to="/notas">Deseos</router-link> |

    <button @click="cerrarSesion">Cerrar sesion</button>
    
  </div>
  <router-view/>
</template>
<script>
  import {mapActions} from 'vuex'
export default {
  methods:{
    //vienen del store index.js
    ...mapActions(['leerToken', 'cerrarSesion'])
  },
  created(){
    this.leerToken()
  }
}
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
