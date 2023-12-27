<template>
  <q-page padding class="position-relative">
    <button 
    class="position-absolute" style="right: 10px;" 
    @click="counter++"
    >
      {{ counter }}
    </button>

    <div class="mb-2">
      <input type="text" v-model="message" 
      @keyup.esc="clearMessage"
      @keyup.enter="alertMessage"
      >
      <button @click="clearMessage">Clear</button>
    </div>
    <h5 v-if="message.length" 
    class="border border-danger"
    >{{ message }}</h5>
    <h6 v-else>No Message Entered</h6>

    <hr>

    <p>Uppercase Message : {{ messageUpperCase }}</p>
    <p>Lowercase message : {{  }}</p>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'IndexPage',
  data(){
    return{
      message : 'I Love Vue JS',
      counter: 0
    }
  },
  computed: {
    // ini buat dia enggk ngaruh misal tombol counter dipencent dia ga load ulang lg
    messageUpperCase(){
      // console.log("fired")
      return this.message.toUpperCase();
    }
  },
  methods: {
    clearMessage(){
      this.message = ''
    },
    alertMessage(){
      alert(this.message);
    },
  }
  
})
</script>

<style>
</style>