<template>
  <div class="center">
      <img alt="Vue logo" src="./assets/logo.png"> <span style="font-size:122px;padding: 0 20px;">+</span> <img class="sirvlogo" alt="Sirv logo" src="https://sirv-cdn.sirv.com/website/img/sirv-logo.svg"/>
    </div>
  <HelloWorld msg="Vue3 + Sirv"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  mounted() {
  if (typeof window.Sirv === 'undefined') {
    let smv = document.createElement('script')
    smv.setAttribute('src', 'https://scripts.sirv.com/sirvjs/v3/sirv.js')
    document.head.appendChild(smv)
    this.loadScript('https://scripts.sirv.com/sirvjs/v3/sirv.js').then(() => {
      window.Sirv.start('.off')
    })
  }
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
  margin-top: 60px;
}
.center {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 200px;
  border: 3px solid green;
}
.sirvlogo {
  max-width:250px;
}
</style>