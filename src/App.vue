<template>
  <TheHeader />
  <TheHero />
  <TheServices />
  <TheAbout />
</template>

<script setup>
import { onMounted } from 'vue';
import AOS from 'aos';
import 'aos/dist/aos.css';
import TheHeader from './components/TheHeader.vue';
import TheHero from './components/TheHero.vue';
import TheServices from './components/TheServices.vue';
import TheAbout from './components/TheAbout.vue';

onMounted(()=>{
  AOS.init();
});

</script>

<style>

</style>