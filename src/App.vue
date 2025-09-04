<template>
  <div class="bg-[#111827] min-h-screen scroll-smooth">
    <Suspense>
      <template #default>
        <div>
          <NavBar/>
          <HeroSection/>
          <AboutSection/>
          <SkillsSection/>
          <ProjectsSection/>
          <ContactSection/>
          <Footer/>
        </div>
      </template>
      <template #fallback>
        <div class="flex justify-center items-center min-h-screen">
          <loadingSpinner/>
        </div>
      </template>
    </Suspense>
  </div>
</template>

<script setup>
import { defineAsyncComponent } from 'vue';
const NavBar = defineAsyncComponent(()=> import('./components/NavBar.vue'))
const HeroSection = defineAsyncComponent(()=> import('./components/HeroSection.vue'))
const AboutSection = defineAsyncComponent(()=> import('./components/AboutSection.vue'))
const SkillsSection = defineAsyncComponent(()=> import('./components/SkillsSection.vue'))
const ProjectsSection = defineAsyncComponent(()=> import('./components/ProjectsSection.vue'))
const ContactSection = defineAsyncComponent(()=> import('./components/ContactSection.vue'))
const Footer = defineAsyncComponent(()=> import('./components/Footer.vue'))
import loadingSpinner from './components/loadingSpinner.vue';

</script>

<style scoped>

</style>
