<template>
    <section
        class="relative flex items-center bg-white py-6 border w-full"
        id="navbar"
    >
        <div class="mx-auto px-4 md:px-6 lg:px-8 container">
            <nav class="flex justify-between items-center">
                <div class="flex items-center">
                    <span>
                        <img
                            src="/src/assets/logo.png"
                            alt="Logo"
                            class="h-12"
                        />
                    </span>
                </div>

                <!-- Desktop Navigation -->
                <div class="hidden md:flex items-center space-x-8">
                    <a
                        v-for="item in navigation"
                        :key="item.name"
                        :href="item.href"
                        class="text-gray-600 hover:text-gray-900"
                    >
                        {{ item.name }}
                    </a>
                </div>

                <!-- Mobile Navigation Button -->
                <div class="md:hidden">
                    <Button variant="ghost" @click="isOpen = !isOpen">
                        <Menu v-if="!isOpen" class="w-6 h-6" />
                        <X v-else class="w-6 h-6" />
                    </Button>
                </div>
            </nav>

            <!-- Mobile Navigation Menu -->
            <div
                v-if="isOpen"
                class="md:hidden top-full left-0 z-10 absolute bg-white py-4 border-gray-200 border-b w-full"
            >
                <div class="mx-auto px-4 container">
                    <div class="flex flex-col space-y-4">
                        <a
                            v-for="item in navigation"
                            :key="item.name"
                            :href="item.href"
                            class="text-gray-600 hover:text-gray-900"
                        >
                            {{ item.name }}
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
import {ref} from "vue";
import {Menu, X} from "lucide-vue-next";
import {Button} from "@/components/ui/button";

const isOpen = ref(false);

const navigation = [
    {name: "Success Stories", href: "#stats"},
    {name: "Our Expertise", href: "#features"},
    {name: "Who We Are", href: "#about"},
    {name: "Connect With Us", href: "#contact"},
];
</script>
