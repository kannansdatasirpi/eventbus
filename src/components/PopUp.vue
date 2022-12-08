<template>
  <div id="event">
    <h2 id="eve">This is PopUp</h2>
    <input type="text" v-model="name" />
    <button id="btn" @click="$emit('close',name)">Close PopUp</button> <!--to emit the event from the child and handle it in the parent component -->
   
  </div>
</template>

<script>

export default {
  name: 'PopUp',
  emits: {
    close:(name) =>  {
      if(!name) {
        return false
      }else {
        return true
      }
      },
    },
  data() {
    return{
      name:''
    }
  }
}
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
