<template>
  <div class="template-container">

    <el-row class="buttonRow">
      <el-col :span="4" :offset="2">
        <div class="grid-content bg-purple">
          <el-button type="primary" @click="addField">添加字段</el-button>
        </div>
      </el-col>
    </el-row>
    <div class="input-item" v-for="(item,index) in templateFieldData" :key="index">
      <el-row :gutter="22" class="input-row">
        <el-col :span="4">
          <div class="grid-content bg-purple">
            <p>字段名</p>
            <el-input v-model="item.fieldName.name" placeholder="请定义字段名"></el-input>
          </div>
        </el-col>
        <el-col :span="4">
          <div class="grid-content bg-purple-light">
            <p>X轴</p>
            <el-input v-model="item.fieldName.X" placeholder="X轴" @input="inputChange(index,'X')"></el-input>
          </div>
        </el-col>
        <el-col :span="4">
          <div class="grid-content bg-purple">
            <p>Y轴</p>
            <el-input v-model="item.fieldName.Y" placeholder="Y轴"></el-input>
          </div>
        </el-col>
        <el-col :span="4">
          <div class="grid-content bg-purple-light">
            <p>高度</p>
            <el-input v-model="item.fieldName.height" placeholder="高度"></el-input>
          </div>
        </el-col>
        <el-col :span="4">
          <div class="grid-content bg-purple">
            <p>宽度</p>
            <el-input v-model="item.fieldName.width" placeholder="宽度"></el-input>
          </div>
        </el-col>
      </el-row>
      <el-row :gutter="22" class="input-row">
        <el-col :span="4">
          <div class="grid-content bg-purple">
            <p>值类型</p>
            <el-select v-model="item.fieldValue.type" placeholder="请选择类型">
              <el-option
                v-for="item in filedType"
                :key="item.value"
                :label="item.label"
                :value="item.value">
              </el-option>
            </el-select>
          </div>
        </el-col>
        <el-col :span="4">
          <div class="grid-content bg-purple-light">
            <p>X轴</p>
            <el-input v-model="item.fieldValue.X" placeholder="X轴"></el-input>
          </div>
        </el-col>
        <el-col :span="4">
          <div class="grid-content bg-purple">
            <p>Y轴</p>
            <el-input v-model="item.fieldValue.Y" placeholder="Y轴"></el-input>
          </div>
        </el-col>
        <el-col :span="4">
          <div class="grid-content bg-purple-light">
            <p>高度</p>
            <el-input v-model="item.fieldValue.height" placeholder="高度"></el-input>
          </div>
        </el-col>
        <el-col :span="4">
          <div class="grid-content bg-purple">
            <p>宽度</p>
            <el-input v-model="item.fieldValue.width" placeholder="宽度"></el-input>
          </div>
        </el-col>
      </el-row>
    </div>
  </div>

</template>

<script>

export default {
  data() {
    return {
      filedType: [{
        value: 'text',
        label: '文本'
      }, {
        value: 'date',
        label: '时间'
      }, {
        value: 'select',
        label: '下拉框'
      }],
      templateFieldData: [
        {
          fieldName: {name: "q1 tcs", X: "0", Y: "0", height: "1", width: "1"},
          fieldValue: {type: "text", X: "1", Y: "0", height: "1", width: "1",}
        },
        {
          fieldName: {name: "q2 tffs", X: "0", Y: "0", height: "1", width: "1"},
          fieldValue: {type: "date", X: "5", Y: "7", height: "7", width: "1",}
        }
      ]
    }
  },
  methods: {
    addField() {
      console.log("addField")
      this.templateFieldData.push({
        fieldName: {name: "", X: "", Y: "", height: "", width: ""},
        fieldValue: {type: "", X: "", Y: "", height: "", width: "",}
      })
    },
    inputChange(index,field) {
      console.log(index,field)
    }
  },

}
</script>

<style scoped>
p {
  word-break: keep-all;
  margin-right: 10px;
}

.input-row {
  display: flex;
  justify-content: center;
  /*margin-top: 10px;*/
}

.input-item {
  margin-top: 20px;
  /*background: rgb(229, 231, 235);*/
  border-radius: 10px;
}


.template-container {
  margin: 50px;

}

:last-child {
  margin-bottom: 0;
}

.bg-purple {
  /*background: #d3dce6;*/
}

.grid-content {
  border-radius: 4px;
  min-height: 36px;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
