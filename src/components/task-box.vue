<template>
<div class="input-container">
    <input id="titleInput" class="input" type="text" v-model="titleInput" placeholder="Type Your Task"/>
    <input class="input2" type="text" v-model="descriptInput" placeholder="Type Description"/>
    <button class="addbtn" @click="addBtn(titleInput, descriptInput)">Add Task</button>
</div>
<section class="box-container">
    <div class="task-box">
      <h2 class="task-header">UnDone Tasks</h2>
            <div class="item" v-for="todo in toDos" :key="todo.index">
            <h2 class='title'>Title :{{todo.title}}</h2>
             <h5 class="des">Description :{{todo.descript}} </h5>
             <button class="cmpbtn" @click="compbtn(todo.id)">Finished</button> 
             <button class="rembtn" @click="rembtn(todo.id)">Remove</button>
        </div>
  </div>
  <div class="comp-box">
      <h2 class="task-header">Completed Tasks</h2>
        <div class="item" style="text-decoration : line-through" v-for="compTodo in compToDos" :key="compTodo.index">
          <h2>Title : {{compTodo.title}}</h2>
          <h5>Description : {{compTodo.descript}}</h5>
        </div>
  </div>
</section>
</template>

<script>
export default {
    name : "TaskBox",
    data(){
        return{
            test4 :"Mamad" ,
            id : 0,
            titleInput : "",
            descriptInput : "",
            toDos:[],
            compToDos:[]
        }
    },
    methods:{
        addBtn(title , descript){
            if(this.titleInput === ""){
                document.getElementById("titleInput").style="border : 1px solid red"
                document.getElementById("titleInput").placeholder= "Please Fill Out The Title Input"
            }else{
                this.toDos.push({id : this.id , title : title , descript : descript , isDone : false})
            }
        },
        rembtn(index){
            this.toDos.splice(index, 1)
            console.log(index)
        },
        compbtn(index){
            let comp = this.toDos[index]
            comp.isDone = true;
            this.compToDos.push(this.toDos[index])
            this.toDos.splice(index,1)
        },
        todoLength(){
            this.$emit("lengthReturner", this.toDos.length)
        }

    }
}
</script>

<style>

</style>