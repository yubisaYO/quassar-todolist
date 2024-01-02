<template>
  <q-page padding class="position-relative">
    
    <!-- <task 
        v-for="(task, i) in tasks"
        :task="task"
        :i = "i"
        :key="i+1"
        >
        {{ task.name }}
    </task> -->
    <!-- <button 
    class="position-absolute" style="right: 10px;" 
    @click="counter++"
    >
      {{ counter }}
    </button>

    <div class="mb-2">
      <input type="text" v-model="message" 
      @keyup.esc="clearMessage"
      @keyup.enter="alertMessage"
      v-bind:class="{ 'error' <task 
        v-for="(task, i) in tasks"
        :task="task"
        :i = "i"
        :key="i+1"
        >
        {{ task.name }}
      </task>: message.length > 22 }"
      ref="messageInput"
      >
      <button @click="clearMessage">Clear</button>
    </div>
    <h5 v-if="message.length" 
    class="border border-danger"
    >{{ message }}</h5>
    <h6 v-else>No Message Entered</h6>

    <hr>

    <p>Uppercase Message : {{ messageUpperCase }}</p>
    <p>Lowercase message : {{ messageLowerCase(message) }}</p> -->

  </q-page>
</template>

<script>
import { defineComponent } from 'vue'
import Task from 'components/Task.vue'

export default defineComponent({
  name: 'IndexPage',
  data(){
    return{
      tasks: [
        {
          name : 'Go to shop',
          dueDate : '2019/05/12',
          dueTime: '18:30'
        },
        {
          name : 'Get bananas',
          dueDate : '2019/05/13',
          dueTime: '14:00'
        },
        {
          name : 'Get apples',
          dueDate : '2019/05/14',
          dueTime: '18:30'
        }
      ]
    }
  },
  methods:{
    deleteTask(idx){
      this.tasks.splice(idx, 1)
    }
  },
  components: {
    'task' : Task
  }
  // computed: {
  //   // ini buat dia enggk ngaruh misal tombol counter dipencent dia ga load ulang lg
  //   messageUpperCase(){
  //     // console.log("fired")
  //     return this.message.toUpperCase() + this.counter;
  //   }
  // },
  // methods: {
  //   clearMessage(){
  //     this.message = ''
  //   },
  //   alertMessage(){
  //     alert(this.message);
  //   },
  //   messageLowerCase(value){
  //     // console.log("dari method");
  //     return value.toLowerCase() + this.counter;
  //   }
  // },
  // beforeCreate(){
  //   console.log("beforeCreate");
  // },
  // created(){
  //   console.log('created');
  // },
  // beforeMount(){
  //   console.log('beforeMount');
  // },
  // mounted(){
  //   console.log(this.$refs.messageInput);
  //   this.$refs.messageInput.className = "bg-green"
  // },
  // beforeUpdate(){
  //   console.log('beforeUpdate')
  // },
  // updated(){
  //   console.log('updated')
  //   console.log();
  // }
})
</script>

<style>
  .error{
    background: pink;
    color: red;
  }
</style>