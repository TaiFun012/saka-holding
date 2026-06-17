<script setup lang="ts">
interface Props {
  phoneNumber?: string;
  telUrl?: string;
}

withDefaults(defineProps<Props>(), {
  phoneNumber: '+90 212 547 08 26',
  telUrl: 'tel:+902125470826'
});
</script>

<template>
  <div class="header-phone-block">
    <a :href="telUrl" class="phone-link">
      <img src="@\assets\icons\phone.svg" class="phone-icon" alt="Phone" />
      <span class="phone-text">{{ phoneNumber }}</span>
    </a>
    <button class="callback-btn">Заказать звонок</button>
  </div>
</template>

<style scoped>
.header-phone-block {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  gap: 2px;
}

.phone-link {
  display: flex;
  align-items: center;
  gap: 8px;
  text-decoration: none;
  transition: opacity 0.2s ease;
}

.phone-icon {
  width: 18px;
  height: 18px;
  object-fit: contain;
  flex-shrink: 0;
}

.phone-text {
  font-size: 20px;
  font-weight: 600;
  color: #ffffff;
  line-height: 1;
  transition: color 0.2s ease;
}

.phone-link:hover .phone-text {
  color: #ffd678; 
}

.phone-link:hover {
  opacity: 0.9;
}

.callback-btn {
  background: none;
  border: none;
  padding: 0;
  font-size: 12px;
  color: #a0aec0;
  text-decoration: underline;
  cursor: pointer;
  transition: color 0.2s ease;
}

.callback-btn:hover {
  color: #ffffff;
}
</style>