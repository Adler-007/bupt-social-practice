<script setup>
import { ref } from "vue";
import Header from "@/views/Header.vue";

const userNameValue = ref("");
const userIdValue = ref("");

function login() {
  if (userNameValue.value == "" || userIdValue.value == "") {
    alert("请输入正确的账号密码");
  } else {
    alert("登录成功！");
  }
}
</script>

<template>
  <div>
    <!-- 头部 -->
    <Header />
    <div class="body">
      <div class="container">
        <div class="left-side">
          <img
            src="@/assets/images/login/loginLeft.jpg"
            alt=""
            class="leftPicture"
          />
          <img
            src="@/assets/images/common/logo.png"
            alt="Neuron Logo"
            class="logo"
          />
        </div>
        <div class="right-side">
          <h1>登录</h1>
          <form action="#" method="">
            <input
              type="text"
              placeholder="用户名"
              id="userName"
              v-model="userNameValue"
            />
            <input
              type="password"
              placeholder="密码"
              id="userId"
              v-model="userIdValue"
            />
            <div class="checkbox-container">
              <div>
                <input type="checkbox" id="remember-me" />
                <label for="remember-me">记住密码</label>
              </div>
              <a href="#" class="forgot-link">忘记?</a>
            </div>
            <input
              type="submit"
              @click="login"
              value="登录"
              class="login-button"
            />
            <hr />
            <div class="others">
              <a href="">
                <img src="@/assets/images/common/phone.png" alt="" />
                <!-- <div class="other-item">12345678901</div> -->
              </a>
              <a href="">
                <img src="@/assets/images/common/wechat.png" alt="" />
                <div class="other-item">
                  <!-- <img src="@/assets/images/common/WeChatQRcode.jpg" alt="" /> -->
                </div>
              </a>
              <a href="">
                <img src="@/assets/images/common/QQ.png" alt="" />
                <div class="other-item">
                  <!-- <img src="@/assets/images/common/qqQRcode.jpg" alt="" /> -->
                </div>
              </a>
              <a href="">
                <img src="@/assets/images/common/more.png" alt="" />
                <div class="other-item">
                  <!-- <img src="@/assets/images/common/moreQRcode.jpg" alt="" /> -->
                </div>
              </a>
            </div>
            <p>没有账号？<router-link to="/Sign">注册</router-link></p>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* 主体部分 */
.body {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 90vh;
}

body .container {
  border-radius: 30px;
}

.container {
  display: flex;
  width: 60%;
  height: 80%;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.128);
}

/* 左侧样式 */
.left-side {
  width: 60%;
  background-color: #e6f7ff;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border-radius: 30px;
  position: relative;
}

.left-side .leftPicture {
  width: 100%;
  height: 100%;
  border-top-left-radius: 30px;
  border-bottom-left-radius: 30px;
}

.logo {
  position: absolute;
  top: 15px;
  left: 15px;
  width: 40px;
  margin-bottom: 20px;
  border-radius: 20px;
}

/* 右侧样式 */
.right-side {
  width: 40%;
  border-top-right-radius: 30px;
  border-bottom-right-radius: 30px;
  background-color: white;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 0 40px;
}

h1 {
  margin-bottom: 30px;
}

input {
  width: 100%;
  padding: 10px;
  margin-bottom: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.checkbox-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  margin-bottom: 20px;
}

.checkbox-container #remember-me {
  width: 20px;
}

.forgot-link {
  text-decoration: none;
  color: #007bff;
  margin-top: -15px;
}

.right-side a {
  color: #007bff;
}

.right-side a:hover {
  text-decoration: underline;
}

.checkbox-container a:hover {
  text-decoration: underline;
  color: #0053ac;
}

.login-button {
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
  padding: 10px 20px;
  cursor: pointer;
}

.others {
  display: flex;
  justify-content: center;
}

.others a:hover {
  transform: translateY(-5px);
  transition: all linear 0.2s;
}

.others img {
  width: 30px;
  height: 30px;
  margin: auto 5px;
}

.other-item {
  display: none;
}
.other-item img {
  /* width: 150px;
  height: 150px; */
  width: 100%;
  height: 100%;
}
.others a:hover .other-item {
  display: block;
  position: absolute;
  top: 120%;
  left: -140%;
}
</style>
