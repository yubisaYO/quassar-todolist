<template>
  <q-page padding class="">
    <q-list padding>
      <q-item
        ta
        v-ripple
        v-for="task in tasks"
        :key="task.id"
        :class="task.completed ? 'bg-green-1' : 'bg-orange-1'"
        style="width: 100%"
      >
        <q-item-section side top>
          <q-checkbox v-model="task.completed" />
        </q-item-section>

        <q-item-section>
          <q-item-label
            :class="{ 'text-strikethrough' : task.completed}">
            {{ task.name }}
          </q-item-label>
        </q-item-section>
        <q-item-section side>
          <div class="row align-items-center">
            <q-icon name="event" size="18px" class="p-0" />
            <div class="col">
              <q-item-label caption>
                {{ task.dueDate }}
              </q-item-label>
              <q-item-label caption>
                <small>{{ task.dueTime }}</small>
              </q-item-label>
            </div>
          </div>
        </q-item-section>
      </q-item>
    </q-list>
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
import { defineComponent } from "vue";
import Task from "components/Task.vue";

export default defineComponent({
  name: "IndexPage",
  data() {
    return {
      tasks: [
        {
          id: 1,
          name: "Go to shop",
          completed: false,
          dueDate: "2019/05/12",
          dueTime: "18.30",
        },
        {
          id: 2,
          name: "Get Bananas",
          completed: false,
          dueDate: "2019/05/12",
          dueTime: "14.00",
        },
        {
          id: 3,
          name: "Buy Chocolate",
          completed: false,
          dueDate: "2019/05/12",
          dueTime: "16.30",
        },
      ],
    };
  },
  methods: {
    deleteTask(idx) {
      this.tasks.splice(idx, 1);
    },
  },
  components: {
    task: Task,
  },
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
});
</script>

<style>
.error {
  background: pink;
  color: red;
}
</style>
