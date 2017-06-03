<template>
  <div class="Test">
  <input type="text" v-modal="title"><br />
  <h1>{{title}}</h1>
  <p v-if="show_name">{{user.first_name}}</p>
  <!-- both lines of code do the same thing except one is a directive -->
  <!-- <p v-text="user.first_name"></p> -->
  <ul>
    <li v-for="item in items">{{item.title}}</li>
  </ul>
  <button v-on:click="greet('Hello World')">Say Greeting</button>
  <br />
  <input type="text" v-on:keyup="press_key" v-on:keyup.enter="enterHit">
  <hr />
  <label> First Name: </label><input type="text" v-model="user.first_name">
  <br />
  <label> Last Name: </label><input type="text" v-model="user.last_name">
  <h3>{{fullname}}</h3>
  <h2>{{msg}}</h2>
  </div>
</template>

<script>
  export default {
    name: 'test',
    props: {
      msg:{
        type: String,
        default: 'Foobar'
      }
    },
    data() {
      return {
        title: 'Hello World',
        user: {
          first_name: 'Natasha',
          last_name: 'Kelly'
        },
        show_name: true,
        items:[
          {title: "Item One"},
          {title: "Item Two"},
          {title: "Item Three"}
        ]
      }
    },
    methods:{
      greet: function(greeting){
        alert(greeting);
      },
      press_key: function(){
        console.log(e.target.value);
      },
      enterHit: function(){
        console.log("You hit enter");
      }
    },
    computed: {
      fullname: function(){
        return this.user.first_name+  ' ' +this.user.last_name
      }
    }
  }
</script>

<style scoped>

</style>
