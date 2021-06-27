<template>
  <el-container>
    <el-aside style="width: 200px;margin-top: 20px">
      <switch></switch>
      <SideMenuIndex></SideMenuIndex>
    </el-aside>
    <el-main>
      <progess></progess>
    </el-main>
  </el-container>
</template>

<script>
// eslint-disable-next-line no-unused-vars
import SideMenuIndex from './SideMenuIndex'
import Progess from './Progress'
export default {
  name: 'AppIndex',
  components: {SideMenuIndex, Progess}
}
</script>

<style scoped>

</style>
