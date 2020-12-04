template:<template>
  <el-form class="login-container">
    <h3 class="login-title">Login</h3>
  <el-form-item>
    <el-input placeholder="account"></el-input>
  </el-form-item>
  <el-form-item>
    <el-input placeholder="password"></el-input>
  </el-form-item>
  <el-checkbox class="login-remember" label-position="left">记住密码</el-checkbox>
  
  <el-form-item>
    <el-button>Login</el-button>
  </el-form-item>
  </el-form>
</template>

<script>
export default {

}
</script>

<style>
.login-container{
  margin: 180px auto;
  width: 350px;
  padding: 35px 35px 15px 35px;
  border: 1px solid #eaeaea;
  border-radius: 15px;
  padding: 35px 35px 15px 35px;
  box-shadow: 0 0 25px #eaeaea;
}
.login-title{
  margin: 0px 0px 35px 0px;
  text-align: center;
  color: #505458;
}
.login-remember{
  margin:0 0 35px 0;
}
</style>