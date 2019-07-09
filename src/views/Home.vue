<template>
  <div class="home">
    <div >
      <ol v-for="task in taskList" :key="task.taskContent">
        {{task.taskContent}}
      </ol>
    </div>
    <el-row>
      <el-col :span='6' v-show="addTaskFormHide">
      <el-input class="input-with-select" >
        <i slot="suffix" class="cursor--point el-input__icon el-icon-date"></i>
      </el-input>
      <el-button type="primary">添加</el-button> <el-button @click="cancleAddTask">取消</el-button>
    </el-col>
    </el-row>
    <div class="task--add--btn" @click="addTaskFormHide = true">
      <i class="el-icon-plus"></i> 添加任务
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue} from 'vue-property-decorator';
import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src

interface Task {
  taskId?: number;
  taskContent: string;
}

@Component
export default class Home extends Vue {
  public taskList: Task[] = [];
  public addTaskFormHide: boolean = false;

  public cancleAddTask(){
    
  }
}
</script>

<style lang="scss" scope>
.home{
  padding: 20px;
  .task--add--btn{
    cursor: pointer;
    padding: 10px 0;
  }
  .input-with-select .el-input-group__prepend {
    background-color: #fff;
  }
  .cursor--point{
    cursor: pointer;
  }
}
</style>
