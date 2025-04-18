<template>
    <div class="relative">
        <Navbar />
        <HeroSection />
        <AboutSection />
        <StatsSection />
        <FeaturesSection />
        <ProjectsSection />
        <TeamSection />
        <ContactSection />
        <FooterSection />
    </div>
</template>

<script setup lang="ts">
import Navbar from "@/components/custom/Navbar.vue";
import HeroSection from "@/components/custom/HeroSection.vue";
import AboutSection from "./custom/AboutSection.vue";
import FeaturesSection from "@/components/custom/FeaturesSection.vue";
import StatsSection from "@/components/custom/StatsSection.vue";
import ContactSection from "@/components/custom/ContactSection.vue";
import FooterSection from "@/components/custom/FooterSection.vue";
import TeamSection from "@/components/custom/TeamSection.vue";
import ProjectsSection from "@/components/custom/ProjectsSection.vue";
</script>

<style scoped></style>
