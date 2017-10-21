<template>
  <div class="login">
    <el-container class="login-container">
      <el-header></el-header>
      <el-main>
        <div class="login-main">
          <div class="login-main_system-name">
            {{systemName}}
          </div>
          <el-form class="login-main_form"
                   :rules="rules"
                   :model="loginForm">
            <el-form-item prop="userName">
              <el-input placeholder="请输入帐户"
                        v-model="loginForm.userName">
                <i v-if="loginForm.userName"
                   slot="suffix"
                   class="el-input__icon el-icon-circle-close"
                   @click="loginForm.userName = ''"></i>
              </el-input>
            </el-form-item>
            <el-form-item prop="password">
              <el-input placeholder="请输入密码"
                        type="password"
                        v-model="loginForm.password">
                <i v-if="loginForm.password"
                   slot="suffix"
                   class="el-input__icon el-icon-circle-close"
                   @click="loginForm.password = ''"></i>
              </el-input>
            </el-form-item>
            <el-form-item>
              <el-button class="login-form_login-button"
                         type="primary"
                         @click="submitForm('')">登录
              </el-button>
            </el-form-item>
          </el-form>
        </div>
      </el-main>
      <el-footer class="login-footer">
        友房科技
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
        },
        rules: {
          userName: [
            {required: true, message: '请输入用户名', trigger: ['blur','change']}
          ],
          password: [
            {required: true, message: '请输入密码', trigger: ['blur','change']}
          ]
        }
      }
    },
    methods: {
      submitForm: function () {
        this.$message({
          message: '恭喜你，这是一条成功消息',
          type: 'success'
        });
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
