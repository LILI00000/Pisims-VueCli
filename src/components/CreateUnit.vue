
<template>
  <el-form :model="form" ref="form">
    <el-row>
      <el-col :span="2">
        <el-form-item label="单位编号："></el-form-item>
      </el-col>
      <el-col :span="10">
        <el-input :value="onGetMD5()" :disabled="true"></el-input>
      </el-col>
    </el-row>
    <el-row>
      <el-col :span="2">
        <el-form-item label="单位全称："></el-form-item>
      </el-col>
      <el-col :span="10">
        <el-input v-model="form.DWQC"></el-input>
      </el-col>
    </el-row>
    <el-row>
      <el-col :span="2">
        <el-form-item label="单位简称："></el-form-item>
      </el-col>
      <el-col :span="10">
        <el-input v-model="form.DWJC"></el-input>
      </el-col>
    </el-row>

    <el-row>
      <el-col :span="3">
        <el-form-item label="单位拨款类型："></el-form-item>
      </el-col>
      <el-col :span="9">
        <el-input v-model="form.BKLX" placeholder="一类全额或二类差额"></el-input>
      </el-col>
    </el-row>
    <el-row>
      <el-col :span="2">
        <el-form-item label="编制总数："></el-form-item>
      </el-col>
      <el-col :span="10">
        <el-input v-model="form.BZZS"></el-input>
      </el-col>
    </el-row>
    <el-row>
      <el-col :span="5">
        <el-button type="primary">创建单位</el-button>
      </el-col>
      <el-col :span="2">
        <el-button @click="onclose()">取消</el-button>
      </el-col>
    </el-row>
  </el-form>
</template>
<script>
var md5 = require("md5");

console.log(md5("message"));
export default {
  name: "CreateUnit",
  data() {
    return {
      form: {
        DWBH: "",
        DWQC: "",
        DWJC: "",
        BKLX: "",
        BZZS: "",
        delivery: false,
        type: [],
        resource: "",
        desc: ""
      }
    };
  },
  methods: {
    onGetMD5: function() {
      return md5(this.form.DWQC + this.form.DWJC);
    },
    onSubmit() {},
    onclose() {}
  }
};
</script>

<style scoped>
.el-input {
  margin: 0;
}
.el-col {
}
</style>