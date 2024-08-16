<script>
  export default{
    data(){
        return{
          name: 'John Doe',
          status: 'pending',
          tasks: [
            'Task one', 'Task two', 'Task three'
          ],
          link: 'https://www.google.com'
        }; 
    },
    methods:{
      toggleStatus(){
        if(this.status === 'active'){
          this.status = 'pending';
        }else if(this.status === 'pending'){
          this.status = 'inactive';
        }else{
          this.status = 'active';
        }
      }
    }
  };
</script>

<template>
  <h2>{{ name }}</h2>
  <p v-if="status === 'active'">User is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else="status">User is inactive</p>

  <h3>Tasks: </h3>
  <ul>
    <li v-for="task in tasks" :key="task">{{ task }}</li>
  </ul>
  <div>
    <a v-bind:href="link">Click for Google</a>
  </div>
  <div>
    <a :href="link">Click for Google</a>
  </div>
  <br>
  <button @click="toggleStatus">Change status</button>
</template>

