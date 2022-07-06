<template>
  <div id="app">
    <!-- <input type="text" v-model="message">
    {{message}} -->
    <!-- <div v-if="show">
      vue.js ep 1
    </div> -->
    <!-- <div v-for="(animals, i) in animal" :key="i">
      {{animals}}
    </div> -->
    <!-- <button v-on:click="submit">
      Greeting
    </button> -->
    <!-- {{ message }} -->
    <!-- <div v-for="value in money" :key="value">
      {{ numberSign(value) }}
    </div> -->
    <!-- <input type="text" v-model="num1">
    <input type="text" v-model="num2">
    {{result}}
    <div :class=" {'center': active} ">
      <button v-on:click="messageWatch">Watch</button>
      <button v-on:click="setActive">Active</button>
    </div> -->
    <div>
      <input type="text" placeholder="Name" v-model="add.name">
      <input type="number" placeholder="Age" v-model="add.age">
      <button 
        v-if="editState"
        @click="updateForm()">Update</button>
      <button 
        v-else
        @click="addForm()">submit
      </button>
    </div><br>
    <table>
      <tr>
        <th>Name</th>
        <th>Age</th>
        <th></th>
        <th></th>
      </tr>
      <tr v-for="(person, i) in personal" :key="i">
        <td>{{person.name}}</td>
        <td>{{person.age}}</td>
        <td><button @click="setUpdate(person, i)">Edit</button></td>
        <td><button @click="deleteForm(i)">Delete</button></td>
      </tr>
    </table>
  </div>
</template>

<script>


export default {
  name: 'App',
  data (){
    return {
      add:
        {
          name:'',
          age:0
        },
      personal: [
        {
          name: 'Mark',
          age: 20
        },
        {
          name: 'Deer',
          age: 19
        },
        {
          name: 'Nam',
          age:25
        }
      ],
      block: 'center',
      active: true,
      message: '',
      show: true,
      num1: null,
      num2: null,
      money:[
        1000,
        2000,
        3000
      ]
      ,
      animal: [
        'pig',
        'cat',
        'dog'
      ],
      editState: false,
      indexBox: null
    }
  },
  watch:{
    message(spyValue){
      console.log(spyValue)
    }
  },
  created() {
    console.log('Created')
  },
  mounted(){
    console.log('mounted')
  }
  ,
  computed:{
    result(){
      return Number(this.num1) + Number(this.num2)
    }
  }
  ,
  methods:{
    // submit(){
    //   if (this.message == '') {
    //     return this.message = 'Hey guys!'
    //   } else {
    //     return this.message = ''
    //   }
    // }
    numberSign (values) {
      return values.toLocaleString()
    },
    messageWatch(){
      this.message = "Hello Watcher"
    },
    setActive(){
      this.active = !this.active
    },
    setDefault() {
      this.add = {
          name:'',
          age:0
        }
    },
    addForm(){
      if (this.add.name == '' || this.add.age == 0) {
        alert("Please type name and age")
      } else {
        this.personal.push(this.add)
        this.setDefault()
      }
      // (this.add == {name:'',age:0}) ? alert("Please type name and age") : this.personal.push(this.add), this.setDefault()
    },
    deleteForm(index){
      this.personal.splice(index, 1)
    },
    setUpdate(person, index){
      this.add.name = person.name
      this.add.age = person.age
      this.editState = true
      this.indexBox = index
    },
    updateForm(){
      this.personal[this.indexBox] = this.add
      this.setDefault()
      this.editState = false
    }
  }
}
</script>

<style scoped>
#app{
  margin:100px;
}
.center{
  text-align: center;
}

table {
  font-family: arial, sans-serif;
  border-collapse: collapse;
  width: 100%;
}     

th{
  background-color: #FFAC9A;
}
td, th {
  border: 1px solid #dddddd;
  text-align: left;
  padding: 8px;
}

tr:nth-child(even) {
  background-color: #FFF3F0;
}
</style>
