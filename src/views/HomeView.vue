<template>
  <div>
    <el-container>
      <el-aside class="aside">
        <!-- 菜单 -->
        <el-row class="tac">
          <el-col>
            <el-menu default-active="2" class="el-menu-vertical-demo" @open="handleOpen" @close="handleClose"
              background-color="#545c64">
              <!-- 
                default-active: 当前激活菜单的索引
                open, close: el-submenu 展开和收起触发的事件
               -->
              <!-- 二级菜单 -->
              <el-submenu index="1">
                <template slot="title">
                  <i class="el-icon-menu"></i>
                  <span slot="title">首页</span>
                </template>
                <el-menu-item-group>
                  <template slot="title">分组一</template>
                  <el-menu-item index="1-1">选项1</el-menu-item>
                  <el-menu-item index="1-2">选项2</el-menu-item>
                </el-menu-item-group>
                <el-menu-item-group title="分组2">
                  <el-menu-item index="1-3">选项3</el-menu-item>
                </el-menu-item-group>
                <el-submenu index="1-4">
                  <template slot="title">选项4</template>
                  <el-menu-item index="1-4-1">选项1</el-menu-item>
                </el-submenu>
              </el-submenu>
              <el-menu-item index="2">
                <i class="el-icon-menu"></i>
                <span slot="title">导航二</span>
              </el-menu-item>
              <el-menu-item index="3" disabled>
                <i class="el-icon-document"></i>
                <span slot="title">导航三</span>
              </el-menu-item>
              <el-menu-item index="4">
                <i class="el-icon-setting"></i>
                <span slot="title">导航四</span>
              </el-menu-item>
            </el-menu>
          </el-col>
        </el-row>




      </el-aside>
      </el-container>
    </div>
</template>
<script>
import instance from '@/api/api'
export default {
  name:"HomeView",
  created(){

    instance.get("/aa").then(res => console.log(res))
  }
}
</script>
<style scoped lang="scss">
.home{
  .aside{
    margin: 0;
    padding: 0;
    .el-menu-vertical-demo{
      height: 100vh;
    }
  }
}
</style>