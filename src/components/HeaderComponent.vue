<template>
    <div class="header"  :style="{ backgroundColor: loggedIn ? headerColor :'#8034eb',}">
      <div class="logo">
        <img src="@/assets/logo (black).svg" alt="Logo" />
      </div>
      <div class="userInfo" v-if="loggedIn">
        <div class="avatar" :style="{ backgroundColor: userAvatarColor }">
          <span class="userAvatarText">{{ user.name.charAt(0) }}</span>
        </div>
        <div class="userDetails">
          <p>{{ full_name }}</p>
          <button @click="logout" class="logoutButton">LOGOUT</button>
        </div>
      </div>
      <div v-else>
        <button @click="login" class="loginButton">LOGIN</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        loggedIn: false,
        user: {
          name: "Kristers",
          surname: "Skrebs",
          code: "IT21022"
        },
      };
    },
    computed: {
      full_name() {
        return `${this.user.name} ${this.user.surname}`;
      },
      userAvatarColor() {
        return "#" + Math.floor(Math.random() * 16777215).toString(16);
      },
    },
    methods: {
      login() {
        const confirmLogin = window.confirm("Do you want to log in?");
        if (confirmLogin) {
          this.loggedIn = true;
          this.$emit("login");
        }
      },
      logout() {
        const confirmLogout = window.confirm("Do you want to log out?");
        if (confirmLogout) {
          this.loggedIn = false;
          this.$emit("logout");
        }
      },
    },
  };
  </script>
  
<style scoped>
.header {
  background-color: #333;
  color: #fff;
  padding: 20px;
  text-align: center;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1000;
}

.loginButton, .logoutButton {
  background-color: #3498db;
  color: #fff;
  padding: 10px 20px;
  border: none;
  cursor: pointer;
  font-size: 14px;
  margin-right: 10px;
}

.avatar {
  color: #fff;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  font-size: 20px;
  margin-right: 10px;
}

.userDetails {
  display: inline-block;
}
</style>