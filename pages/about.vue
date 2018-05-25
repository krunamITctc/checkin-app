<template>
  <div>
    <h1 v-if="ok">About ITCTC</h1>
    <h2 v-show="ok"> <b>{{newName}}</b></h2>
    <br> name : <input type="text" :value="name.substr(m,3)">
    <br> name2 : <input type="text" v-model="name">
    <br> Password : <input type="password" v-model="name">
    <br><button @click="doSave">Login</button>   
  
    <table border="1">
      <thead>
        <tr>
         <th>ลำดับที่.</th>
         <th>ชื่อ.</th>
         <th>หน่วยงาน.</th>
         </tr>
      </thead>
     <tbody>
       <tr v-for="(mem,i) in members" :key="mem.id" 
           :class="{gray: mem.id % 2 === 0}"
          class="text"
        >
         <td >{{i+1}}</td>
         <td>{{mem.name}}</td>
         <td>{{mem.org}}</td>
       </tr>
       <tr v-for="(item,k) in {id:1,name:'kruname'}" :key="k" >
         <td>{{k}}={{item}}</td>
       </tr>
       <tr v-for="i in 10" :key="i">
         <td>{{i+10}}</td>

       </tr>
     </tbody>

    </table>
     <br><button @click="doAdd">Add</button>   
  </div>
</template>
<script>
export default {
  data(){
    return{
      code: '001',
      name: 'sunisa pafun',
      ok:true,
      members:[
        {id:1,name:'Name1',org:'CTC'},
        {id:2,name:'Name2',org:'CTC'},
        {id:3,name:'Name3',org:'CTC'},
      ],
    }
  },
  computed: {
    upperName(){
      return this.name.toUpperCase()
    },
    newName() {
      var tmp = this.name.split(' ')
      if (tmp.length === 1) {
        return this.name
      }
      return tmp[0] + ' ' + tmp[1].substr(0, 1)
    },
  },
    
   methods: {
    doSave() {
      this.name += '*'
      this.ok=!this.ok
    },
    doAdd() {
      let id = this.members.length + 1
      this.members.push({
        id,
        name: `Name${id}`,
        org: `Org${id}`,
      })
    },
  },
  
}
</script>
<style>
.text {
  color: blue;
}
.gray{
  background-color: #eee;
}
</style>
