<template>
<h1 class="the-title">toDoList</h1>
<div class="toDo">

  <form action="" class="toDo__form">
    <input type="text" name="" id="" class="toDo__base-input" placeholder="Задача"
    v-model="base">
    <input type="text" name="" id="" class="toDo__detail-input" placeholder="детали Задачи"
    v-model="detail">
    <button type="button" @click="addTask()">Добавить</button>
  </form>

  <p class="toDo__no" v-if="tasks.length === 0">Ещё нет ни одной задачи</p>

  <Tasks :myTasks="tasks" :deleteTask="deleteTask"></Tasks>

</div>
</template>

<style scoped>
.toDo{
  display: flex;
  flex-direction: column;
  max-width: 70%;
  width: 100%;
}
.toDo__list{
  margin-top: 20px;
  display: flex;
  flex-direction: column;
  gap: 10px;
  list-style: none;
  padding: 0;
}
.toDo__item{
  border: 1px solid teal;
  border-radius: 8px;
  padding: 20px;
  padding-bottom: 10px;

  display: flex;
  justify-content: space-between;
  gap: 20px;
  align-items: flex-start;
}
</style>

<script>
  import Tasks from './components/Tasks.vue'
  export default{
    component:{Tasks},
    data(){
      return{
        tasks:[],
        base:'',
        detail:'',
      }
    },
    methods:{
      addTask(){
        this.tasks.push({
          baseText: this.base,
          detailText: this.detail,
        },
        )
      },
      deleteTask(index){
        this.tasks.splice(index,1)
      }
    }
  }
</script>