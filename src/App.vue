<template>
  <div id="app">
    {{ counter }}<hr/>
    <button @click="counter=counter+1">Click1</button><br/>
    <button @click="clicked">Click2</button>


    <h1>{{ message}}</h1><br/>
    <span v-text="message"></span><br/>

    <input type="text" v-model="message" />

    <hr/>
    <h1 v-show="isShow">Hello!</h1>
    
    <hr/>
    <div v-bind:key="emp.id" v-for="emp in emplayees">
        <span v-bind:class="(emp.Salary>90000)? 'high' : (emp.Salary>=30000)? 'medium' :'low' ">

        {{ emp.name}}
        </span>

        <span v-if="emp.Salary>90000">***</span>
        <span v-else-if="emp.Salary>=30000">**</span>
        <span v-else>*</span>
    </div>

    <hr/>
    <a v-bind:href="urlSKRU">SKRU</a>
    <hr/>
    <img v-bind:src="require('@/assets/' + pictureName +'.png')" width ="200px "/>
    <hr/>
    <select v-model="message">
      <option value="Bread">Bread</option>
      <option value="Candy">Candy</option>
      <option value="Coke">Coke</option>
    </select>
    <hr/>
    <textarea v-model="message"></textarea>

  </div>
</template>

<script>



export default {
  name: 'App',
  components: {
  },
  data(){
    return{
      counter:0,
      pictureName:"logo",
      urlSKRU:"http://www.skru.ac.th",
      message:"Hello world!",
      isShow: false,
      emplayees: [ 
        {"id":1,"name":"john","Salary": 30000} , 
        {"id":2,"name":"Trump","Salary": 10000} ,
        {"id":3,"name":"Peter","Salary": 99000} 
      ],
    }
  },
  methods:{
    clicked: function(){
      this.counter=this.counter+2;
    }
  },
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
.high{
  color: green;
}
.medium{
  color: yellow;
}
.low{
  color: red;
}
</style>
