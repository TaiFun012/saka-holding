<script setup lang="ts">

</script>

<template>
   <button class="login-btn">
    <img src="@\assets\icons\User.svg" alt="Вход"/>
    <span class="text">Войти</span>
  </button>
</template>

<style scoped>
.login-btn {
  display: flex;
  align-items: left;
  background: none;
  font-size: 14px;
  cursor: pointer;
  transition: all 0.2s;
  border: none;
}

.text {
  color: #ffffff;
}
</style>