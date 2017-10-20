<template>
  <div class="login">
    <el-container class="login-container">
      <el-header>this is a header</el-header>
      <el-main class="login-main">
        <div class="login-main_system-name">
          {{systemName}}
        </div>
        <el-form class="login-main_form"
                 :model="loginForm">
          <el-form-item>
            <el-input placeholder="请输入帐户"
                      v-model="loginForm.userName"></el-input>
          </el-form-item>
          <el-form-item>
            <el-input type="password"
                      placeholder="请输入密码"
                      v-model="loginForm.password"></el-input>
          </el-form-item>
          <el-form-item>
            <el-button class="login-form_login-button"
                       type="primary"
                       @click="submitForm('numberValidateForm')">登录
            </el-button>
          </el-form-item>
        </el-form>
      </el-main>
      <el-footer class="login-footer">
        this is a footer
      </el-footer>
    </el-container>
  </div>
</template>

<script>

  export default {
    name: 'Login',
    data () {
      return {
        systemName: '友爱房产房屋信息系统',
        loginForm: {
          userName: '',
          password: ''
        }
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .login {
    height: 100%;
    background: #000 url('./res/backgroundImage.jpeg') no-repeat center center;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
  }

  .login-container {
    height: 100%;
  }

  .login-main {
    background: rgba(0, 0, 0, 0.4);
    margin: 60px auto;
    height: 400px;
    border: 1px solid #eee;
    border-radius: 10px;
    width: 360px;
    padding: 30px;
  }

  .login-main_system-name {
    margin-top: 60px;
    font-size: 30px;
    color: #fff;
    width: 100%;
    text-align: center;
  }

  .login-main_form {
    margin: 40px auto 0 auto;
    width: 260px
  }

  .login-form_login-button {
    width: 100%;
    font-size: 20px;
    text-indent: 16px;
    letter-spacing: 16px
  }

  .login-footer {
    text-align: center;
    font-size: 16px;
    color: #fafafa;
  }
</style>
