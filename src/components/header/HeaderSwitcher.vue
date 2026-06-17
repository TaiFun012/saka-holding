<script setup lang="ts">
import { ref } from 'vue';
const currentLang = ref<'RU' | 'EN'>('RU');
const setLang = (lang: 'RU' | 'EN') => { currentLang.value = lang; };

</script>

<template>
    <div class="lang-switcher">
    <button :class="{ active: currentLang === 'RU' }" @click="setLang('RU')">RU</button>
    <span class="separator">/</span>
    <button :class="{ active: currentLang === 'EN' }" @click="setLang('EN')">EN</button>
  </div>
  
</template>

<style>
.lang-switcher {
  display: flex;
  align-items: center;
  gap: 4px;
  font-size: 14px;
  font-weight: 500;
}
button {
  background: none;
  border: none;
  padding: 0;
  color: #838383;
  cursor: pointer;
}

button.active {
  color: #ffffff;
  font-weight: 500;
}

.separator { color: #ffffff; }

</style>