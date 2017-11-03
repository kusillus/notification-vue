<template>
  <div id="app">
    <button @click="showNotify('Modulo X agregado','Se agrego correctamente', 1)">
      Este click
    </button>
    <button @click="showNotify('Modulo Y no agregado','Se produjo un error al agregar', 0)">
      Otro click
    </button>
    <notification
      :notifyArray="notify"
      v-if="true">
    </notification>
  </div>
</template>

<script>
import notification from './components/cNotification.vue'
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      showAlert: false,
      notifyTitle: '',
      notifyDescription: '',
      notifyStatus: 0,
      notify: [
        {'title': 'Modulo uno agregado', 'description': 'Se ha agregago correctamente al array', 'status': 1},
        {'title': 'Modulo dos no agregado', 'description': 'No se ha podido agregar al array', 'status': 0}
      ]
    }
  },
  watch: {
    notify: function (el) {
      console.log(el.length)
      if(el.length > 0) {
        this.splitItem()   
      }
    }
  },
  methods: {
    showNotify: function (title, description, status) {
      this.showAlert = true
      let item = {'title': title, 'description': description, 'status': status}
      this.notify.push(item)
      let timeOut = window.setTimeout(this.hideNotify, 2000)
    },
    splitItem(){
      let aux = window.setTimeout(this.deleteItem, 1800)
    },
    deleteItem: function () {
      this.notify.splice(0,1)
    },
    hideNotify: function () {
      this.showAlert = false
    }
  },
  components: {
    notification
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Roboto', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  
}
body{
  background-color: rgba(0, 0, 0, 0.1)
}

// h1, h2 {
//   font-weight: normal;
// }

// ul {
//   list-style-type: none;
//   padding: 0;
// }

// li {
//   display: inline-block;
//   margin: 0 10px;
// }

// a {
//   color: #42b983;
// }
</style>
