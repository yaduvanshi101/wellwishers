<script setup lang="ts">
import {Badge} from "@/components/ui/badge";
import {Card, CardContent} from "@/components/ui/card";
import {Image as ImageIcon, ExternalLink} from "lucide-vue-next";

interface Project {
    title: string;
    description: string;
    image: string;
    link?: string;
}

const projects: Project[] = [
    {
        title: "DonorZilla",
        description:
            "A healthcare platform connecting doctors and patients for online appointments, while facilitating blood donation by matching donors with recipients based on proximity and need.",
        image: "/src/assets/DonorZilla.jpg",
        link: "https://www.donorzilla.com",
    },
    {
        title: "ProFood",
        description:
            "An online restaurant management system where owners can directly deliver food to customers and gather demand insights, helping them understand customer preferences and grow their business.",
        image: "/src/assets/ProFood.jpg",
        link: "https://www.profood.com",
    },
    {
        title: "Fresh Daily",
        description:
            "A successful offline bakery brand offering freshly baked goods directly to customers. Known for quality ingredients and artisanal techniques that have built a loyal local customer base.",
        image: "/src/assets/freshDaily.jpg",
    },
];
</script>

<template>
    <section id="works" class="bg-white py-12 md:py-20 w-full">
        <div class="mx-auto px-4 md:px-6 lg:px-8 container">
            <!-- Header -->
            <div class="space-y-4 mb-10 text-center">
                <Badge variant="outline" class="mb-4">
                    <ImageIcon class="mr-2 size-4" />
                    Our Work
                </Badge>
                <h2
                    class="font-bold text-3xl md:text-4xl lg:text-5xl tracking-tight"
                >
                    Projects That Make Us Proud
                </h2>
                <p class="mx-auto max-w-2xl text-muted-foreground md:text-lg">
                    Explore some of the digital experiences we've crafted for
                    our clients.
                </p>
            </div>

            <!-- Projects Grid -->
            <div class="gap-8 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3">
                <Card
                    v-for="project in projects"
                    :key="project.title"
                    class="flex flex-col bg-white shadow-sm border border-primary rounded-xl overflow-hidden"
                >
                    <img
                        :src="project.image"
                        :alt="project.title"
                        class="px-2 border w-full object-fit aspect-video"
                    />
                    <CardContent class="flex flex-col flex-1 p-6">
                        <h3 class="font-bold text-2xl tracking-tight">
                            {{ project.title }}
                        </h3>
                        <p class="flex-1 mb-4 text-muted-foreground">
                            {{ project.description }}
                        </p>
                        <div v-if="project.link" class="mt-auto">
                            <a
                                :href="project.link"
                                target="_blank"
                                rel="noopener"
                                class="inline-flex items-center font-medium text-primary hover:underline"
                            >
                                View Project
                                <ExternalLink class="ml-1 size-4" />
                            </a>
                        </div>
                    </CardContent>
                </Card>
            </div>
        </div>
    </section>
</template>
