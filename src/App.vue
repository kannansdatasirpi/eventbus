<!--to allow components to send 
and receive events outside beyond the parent-child relationship, producing a result known as the event bus-->

<template>
  <button @click="showPopup =true">Show Popup</button>
  <PopUp v-show="showPopup" @close="closePopup" />      <!--conditionally render it-->
</template>

<script>
import PopUp from './components/PopUp.vue'

export default {
  name: 'App',
  components: {
    PopUp
  },
  data(){
    return{
      showPopup: false          //using this data property to conditionally render it.
    }
  },
  methods: {
    closePopup(name) {
      this.showPopup = false    //set the data property false hide the component pass some 
      console.log('name',name);
    }
  }
}
</script>
<!--One drawback of the event bus model is that you must ensure that event names are unique within 
the application so that the meaning of events is not confused. If your application becomes too large to allow 
easy management of event names,-->
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
