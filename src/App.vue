<template>
  <div class="todo-container">
    <div class="todo-wrap">
      <Header :addTodo="addTodo"></Header>
      <Main :todos="todos" :updateOne="updateOne"></Main>
      <Footer></Footer>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
import Header from '@/components/Header'
import Main from '@/components/Main'
import Footer from '@/components/Footer'

export default {
  components:{
    Header,
    Main,
    Footer
  },
  data(){
    return {
      todos:[
        {id:1,content:'谢可寅',isOver:true},
        {id:2,content:'韦豆豆',isOver:false},
        {id:3,content:'蔡蔡',isOver:true},
      ]
    }
  },
  methods:{
    addTodo(obj){
      this.todos.unshift(obj)
    },
    updateOne(index,val){
      this.todos[index].isOver=val
    }
  }
}
</script>

<style scoped>
/*app*/
.todo-container {
  width: 600px;
  margin: 0 auto;
}
.todo-container .todo-wrap {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}
</style>
