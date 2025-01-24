<template>
  <ul class="toDo__list">
    <li class="toDo__item" v-if="tasks.length>0" v-for="(task, index) in myTasks" >
      <div class="toDo__content">
        <p class="toDo__base-text">{{ task.baseText }}</p>
        <p class="toDo__detail-input">{{ task.detailText }}</p>
      </div>
      <div class="toDo__btns">
          <button type="button" class="toDo__btns-remove" @click="deleteTask(index)">Удалить</button>
      </div>
    </li>
  </ul>
</template>

<style></style>

<script>
export default{
  props:{
        myTasks:{
          type: Array,
          required: true,
        },
        deleteTask:{
          type: Function,
          required: true
        }
    },
    data(){
        return{

        }
    },
    methods:{

    },

}
</script>