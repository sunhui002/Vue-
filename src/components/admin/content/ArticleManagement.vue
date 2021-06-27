<template>
  <div class="block">
    <el-row>
      <el-col :span="12">
        <div class="grid-content bg-purple-dark">
          <el-calendar v-model="value">
          </el-calendar>
       </div>
      </el-col>
      <el-col :span="12">
        <div class="grid-content bg-purple-light">
          <el-input
            type="textarea"
            autosize
            placeholder="请输入内容"
            v-model="textarea2">
          </el-input>
          <div style="margin: 20px 0;"></div>
          <el-input
            type="textarea"
            :autosize="{ minRows: 2, maxRows: 4}"
            placeholder="请输入内容"
            v-model="textarea3">
          </el-input>
        </div></el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  name: 'ArticleManagement',
  data () {
    return {
      value: new Date(),
      pickerOptions1: {
        disabledDate (time) {
          return time.getTime() > Date.now()
        },
        shortcuts: [{
          text: '今天',
          onClick (picker) {
            picker.$emit('pick', new Date())
          }
        }, {
          text: '昨天',
          onClick (picker) {
            const date = new Date()
            date.setTime(date.getTime() - 3600 * 1000 * 24)
            picker.$emit('pick', date)
          }
        }, {
          text: '一周前',
          onClick (picker) {
            const date = new Date()
            date.setTime(date.getTime() - 3600 * 1000 * 24 * 7)
            picker.$emit('pick', date)
          }
        }]
      },
      value1: '',
      value2: ''
    }
  }
}
</script>

<style>
  .el-row{
    margin-bottom: 20px;
  }
  .el-col {
    border-radius: 4px;
  }
  .bg-purple-dark {
    background: #99a9bf;
  }
  .grid-content {
    border-radius: 4px;
    min-height: 36px;}
  .bg-purple-light {
    background: #e5e9f2;
  }
</style>
