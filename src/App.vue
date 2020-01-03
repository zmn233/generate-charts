<template>
  <div id="app">
    <el-row>
      <el-col :span="4">
        <el-select v-model="tableName" placeholder="请选择表名">
          <el-option
            v-for="item in tableNames"
            :key="item.value"
            :label="item.value"
            :value="item.value">
          </el-option>
        </el-select>
      </el-col>
      <el-col :span="4">
        <el-select v-model="chartType" placeholder="请选择展示效果" v-if="tableName !== ''">
          <el-option
            v-for="item in chartTypes"
            :key="item.label"
            :label="item.label"
            :value="item.value">
          </el-option>
        </el-select>
      </el-col>
      <el-col :span="4">
        <el-select v-model="firstField" placeholder="请选择一维字段" v-if="chartType !== ''">
          <el-option
            v-for="item in firstFields"
            :key="item.label"
            :label="item.label"
            :value="item.value">
          </el-option>
        </el-select>
      </el-col>
      <el-col :span="4">
        <el-select v-model="secondField" placeholder="请选择二维字段" v-if="chartType === 'line' || chartType === 'bar'">
          <el-option
            v-for="item in secondFields"
            :key="item.label"
            :label="item.label"
            :value="item.value">
          </el-option>
        </el-select>
      </el-col>
      <el-col :span="4">
        <el-button type="primary">确认</el-button>
      </el-col>
    </el-row>
    <el-row></el-row>
  </div>
</template>

<script>
export default {
  name: 'app',
  components: {
  },
  data () {
    return {
      tableName: '',
      chartType: '',
      tableNames: [
        {
          value: 'table1'
        },
        {
          value: 'table2'
        },
        {
          value: 'table3'
        }
      ],
      chartTypes: [
        {
          value: 'pie',
          label: '饼图'
        },
        {
          value: 'line',
          label: '折线图'
        },
        {
          value: 'bar',
          label: '柱状图'
        },
        {
          value: 'table',
          label: '表格'
        }
      ],
      firstFields: [
        {
          label: '',
          value: ''
        },
        {
          label: '',
          value: ''
        },
        {
          label: '',
          value: ''
        }
      ],
      secondFields: [
        {
          label: '',
          value: ''
        },
        {
          label: '',
          value: ''
        },
        {
          label: '',
          value: ''
        }
      ]
    }
  },
  methods: {
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
