<template>
  <div>
    <div class="img-div">
      <img alt="Vue logo" src="../assets/images/home-header-bg.jpg">
    </div>
    <div class="login-div" v-show="state === 'login'">
      <div class="header">Welcome</div>
      <div class="content">
        <div class="input-div">
          <label><v-icon name="user"></v-icon></label>
          <input class="input-style" placeholder="Username"/>
        </div>
        <div class="input-div">
          <label><v-icon name="lock"></v-icon></label>
          <input class="input-style" placeholder="Password"/>
        </div>
        <div class="button-div">
          <div class="button" @click="login()">LOGIN</div>
        </div>
        <div class="forgot" @click="state = 'forgot'">
          Forgot Password?
        </div>
        <div class="member">
          Not a Member? <span class="small-action" @click="state = 'signup'">Sign up as Tenant</span>
        </div>
      </div>
    </div>
    <div class="signup-div" v-show="state === 'signup'">
      <div class="header">Sign Up Tenant</div>
      <div class="content">
        <div class="input-div">
          <input class="input-style" placeholder="Name"/>
        </div>
        <div class="input-div">
          <input class="input-style" placeholder="Email"/>
        </div>
        <div class="input-div">
          <input class="input-style" placeholder="Username"/>
        </div>
        <div class="input-div">
          <input class="input-style" placeholder="Password"/>
        </div>
        <div class="input-div">
          <input class="input-style" placeholder="Re-enter Password"/>
        </div>
        <div class="button-div">
          <div class="button" @click="signUp()">SIGN UP</div>
        </div>
        <div class="member">
          Already a Member? <span class="small-action" @click="state = 'login'">Login</span>
        </div>
      </div>
    </div>
    <div class="forgot-div" v-show="state === 'forgot'">
      <div class="header">Forgot Password</div>
      <div class="content">
        <div class="content-text">Please enter your email so we can send you a Reset Link</div>
        <div class="input-div">
          <label><v-icon name="envelope"></v-icon></label>
          <input class="input-style" placeholder="Email"/>
        </div>
        <div class="button-div">
          <div class="button" @click="forgotPassword()">SEND</div>
        </div>
        <div class="signin" @click="state = 'login'"> Sign In</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data () {
    return {
      state: 'login'
    };
  },
  methods: {
    login: function () {
      alert('logged in');
    },
    signUp: function () {
      alert('signed up');
    },
    forgotPassword: function () {
      alert('forgotPassword');
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

@import url(https://fonts.googleapis.com/css?family=Roboto:300,400,500,600,700);
$primaryColor: #6785ff;
div {
  font-family: 'Roboto', sans-serif;
}
.img-div {
  z-index: 0;
  top: 0;
  left: 0;
  position: fixed;
  img {
    width: 100%;
  }
}
.login-div, .signup-div, .forgot-div {
  position: relative;
  border-radius: 10px;
  margin: 0 auto;
  width: 400px;
  height: 400px;
  margin-top: calc(25% - 200px);
  z-index: 100;
  background: white;
  box-shadow: 0 2px 2px 0 rgba(0,0,0,.14), 0 3px 1px -2px rgba(0,0,0,.2), 0 1px 5px 0 rgba(0,0,0,.12);

  .header {
    text-align: center;
    font-weight: 300;
    font-size: 32px;
    color: black;
    padding: 10px;
    padding-top: 30px;
    margin-bottom: 40px;
  }
}
.signup-div {
  height: 500px;
  .content {
    .input-style {
      width: 90%;
    }
  }
}
.content-text {
  margin: 60px;
  margin-top: 0px;
}
.signin {
  position: absolute;
  bottom: 20px;
  right: 60px;
  cursor: pointer;
  color: $primaryColor;
}
.input-div {
  border-bottom: 2px solid #f7f7f7;
  margin: 0px 60px 20px;
  label {
    vertical-align: -4px;
    margin-right: 20px;
    color: $primaryColor;
  }
  .input-style {
    width: 70%;
    padding: 5px;
    border: none;
    border-radius: 6px;
    outline: none;
    transition: all 0.1s cubic-bezier(0.1, 0.7, 1.0, 0.1);
  }
}
.button-div {
  width: 100%;
  text-align: center;
}
.button {
    display: inline-table;
    width: 40%;
    background: $primaryColor;
    padding: 10px;
    color: white;
    border-radius: 2px;
    margin: 10px;
    cursor: pointer;
    &.no-back {
      background: none;
      border: 2px solid $primaryColor;
      color: black;
    }
  }
  .forgot {
    font-size: 12px;
    color: #848484;
    cursor: pointer;
  }
  .member {
    margin-top: 20px;
    font-size: 14px;
    .small-action {
      cursor: pointer;
      color: $primaryColor;
      &:hover {
        text-decoration: underline;
      }
    }
  }
</style>
