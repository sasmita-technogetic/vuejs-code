<template>
    <div>
     <h1>For loop in Vue js</h1>
     <table border="1px">
         <tr>
             <td>id</td>
             <td>name</td>
             <td>email</td>
         </tr>
         <tr v-for="item in users" :key="item.id" >
             <td>{{item.id}}</td>
             <td>{{item.name}}</td>
             <td>{{item.email}}</td>
         </tr>
     </table>
   </div>
     
</template>
<script>
export default {
    name:'Home',
    props:{
        data: String
    },
    data(){
        return {
            users:[
                {id:1,name:'Sasmita',email:"sasmita@gmail.com"},
                {id:2,name:'Rajesh',email:"rajesh@gmail.com"},
                {id:3,name:'saif',email:"saif@gmail.com"},
                {id:4,name:'yash',email:"yash@gmail.com"},
                {id:5,name:'Subham',email:"subham@gmail.com"},
            ]
        }
    },
    
}
</script>