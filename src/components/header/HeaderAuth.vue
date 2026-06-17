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
  gap: 6px;
  background: none;
  padding: 6px 12px;
  border-radius: 6px;
  font-size: 14px;
  cursor: pointer;
  transition: all 0.2s;
}
.login-btn:hover { background-color: #000000; border-color: #ffffff; }

.text {
  color: #ffffff;
}
</style>