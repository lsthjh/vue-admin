<template>
  <div class="index-view">
    <div class="ipt-wrap">
      <div class="flex sing-options">
        <el-button color="none" :dark="isDark" plain>登录</el-button>
        <el-button color="none" :dark="isDark">注册</el-button>
      </div>
      <el-form
        label-position="top"
        label-width="100px"
        :model="formLabelAlign"
        style="max-width: 460px"
      >
        <el-form-item label="邮箱">
          <el-input v-model="formLabelAlign.name" />
        </el-form-item>
        <el-form-item label="密码">
          <el-input v-model="formLabelAlign.region" />
        </el-form-item>
        <el-form-item label="验证码">
          <el-input v-model="formLabelAlign.type" />
          <el-button type="success">获取验证码</el-button>
        </el-form-item>
        <el-form-item class="sign_btn" label="默认样式">
          <el-input value="注册" />
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>

<script>
import { reactive, ref } from "vue";

const labelPosition = ref("right");

const formLabelAlign = reactive({
  name: "",
  region: "",
  type: "",
});

export default {
  setup() {
    return {
      labelPosition,
      formLabelAlign,
    };
  },
};
</script>

<style lang="less" scoped>
.index-view {
  height: 100vh;
  display: flex;
  color: white;
  background-color: #32495f;

  .ipt-wrap {
    margin: 200px auto 0;
    width: 300px;
    .sing-options {
      margin-bottom: 40px;
    }

    /deep/.el-form-item__label {
      color: white;
    }

    /deep/.el-form-item__content {
      flex-wrap: nowrap;

      .el-button--success {
        margin-left: 20px;
      }
    }

    .sign_btn {
      /deep/.el-form-item__label {
        color: gray;
        text-align: end;
      }

      /deep/.el-input__wrapper {
        background-color: pink;

        .el-input__inner {
          color: white;
          text-align: center;
        }
      }
    }
  }
}
</style>
