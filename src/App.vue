<template>
  <TheHeader />
  <TheHero />
  <TheServices />
  <TheAbout />
  <TheSpecialists />
  <TheContact />
  <TheFooter />
</template>

<script setup>
import { onMounted } from 'vue';
import AOS from 'aos';
import 'aos/dist/aos.css';
import TheHeader from './components/TheHeader.vue';
import TheHero from './components/TheHero.vue';
import TheServices from './components/TheServices.vue';
import TheAbout from './components/TheAbout.vue';
import TheSpecialists from './components/TheSpecialists.vue';
import TheContact from './components/TheContact.vue';
import TheFooter from './components/TheFooter.vue';

onMounted(()=>{
  AOS.init();
});

</script>
