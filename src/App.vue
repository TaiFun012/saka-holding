<script setup lang="ts">
import AppHeader from '@/components/layout/AppHeader.vue';
import { RouterView } from 'vue-router';
import Navigation from '@/components/ui/Navigation.vue';
import SpecialOffer from '@/components/ui/SpecialOffer.vue';


</script>

<template>
  <AppHeader />
  <Navigation /> 
    <main>
      <router-view />
    </main>
  <SpecialOffer />
  <RouterView />
  <AppFooter />
  
</template>

<style>
body {
  margin: 0;
  padding: 0;
}
</style>