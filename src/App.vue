<template>
  <TheHeader />
  <TheHero />
  <TheServices />
</template>

<script setup>
import { onMounted } from 'vue';
import AOS from 'aos';
import 'aos/dist/aos.css';
import TheHeader from './components/TheHeader.vue';
import TheHero from './components/TheHero.vue';
import TheServices from './components/TheServices.vue';

onMounted(()=>{
  AOS.init();
});

</script>

<style>

</style>