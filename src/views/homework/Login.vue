<template>
  <div class="img">
    <div align="center">
      <el-form
        :model="ruleForm"
        status-icon
        :rules="rules"
        ref="ruleForm"
        label-width="100px"
        class="demo-ruleForm"
      >
        <el-form-item label="用户名">
          <el-input
            type="text"
            v-model="ruleForm.userName"
            @input="change($event)"
          ></el-input>
        </el-form-item>
        <el-form-item label="密码">
          <el-input
            type="password"
            v-model="ruleForm.password"
            autocomplete="off"
            @input="change($event)"
          ></el-input>
        </el-form-item>
        <el-form-item>
          <el-button
            style="width: 100%"
            type="primary"
            @click="submitForm(ruleForm)"
          >
            登录
          </el-button>
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, Ref, ref } from "vue";

export default defineComponent({
  setup() {
    const form = { userName: "", password: "" };
    const ruleForm = ref(form);
    const change = (e: { $forceUpdate: () => void }) => {
      e.$forceUpdate();
    };
    return {
      ruleForm,
      change
    };
  }
});
</script>
<style scoped>
.img {
  background: url("../../image/background.jpg");
  display: flex;
  background-size: cover;
  width: 1920px;
  height: 700px;
  background-attachment: fixed;
}
.demo-ruleForm {
  float: left;
  padding: 40px 90px 0 0;
  margin: 200px 500px;
  background: rgba(238, 234, 234, 0.8);
  border-radius: 3%;
}
</style>
