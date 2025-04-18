<template>
    <section
        id="about"
        class="relative flex items-center bg-white py-8 md:py-16 lg:py-24 w-full scroll-mt-24"
    >
        <div class="mx-auto px-4 md:px-6 lg:px-8 container">
            <!-- Header -->
            <div class="space-y-4 mb-10 text-center">
                <Badge variant="outline" class="mb-4">
                    <Sparkles class="mr-2 size-4" />
                    Our Story
                </Badge>
                <h2
                    class="font-bold text-3xl md:text-4xl lg:text-5xl tracking-tight"
                >
                    The Journey of WellWishers
                </h2>
                <p class="mx-auto max-w-2xl text-muted-foreground md:text-lg">
                    From humble beginnings to a leading digital agency,
                    WellWishers has always been driven by a passion for crafting
                    exceptional digital experiences.
                </p>
            </div>

            <!-- Story Card -->
            <div class="flex justify-center">
                <Card class="shadow-md w-full max-w-3xl">
                    <CardContent class="p-8 md:p-12">
                        <div
                            class="flex md:flex-row flex-col items-center gap-6"
                        >
                            <div>
                                <p
                                    class="mb-4 text-muted-foreground text-lg md:text-xl"
                                >
                                    Founded by a group of passionate creators,
                                    WellWishers began as a small team with a big
                                    vision to help businesses thrive in the
                                    digital world. Over the years, we've grown
                                    into a multidisciplinary agency, excelling
                                    in web and app development, digital
                                    marketing, and UI/UX design.
                                </p>
                                <p class="text-muted-foreground text-base">
                                    Our journey is defined by our commitment to
                                    innovation, quality, and client success.
                                    Every project is a new opportunity to make a
                                    difference, and every client is a valued
                                    partner in our story.
                                </p>
                            </div>
                        </div>
                    </CardContent>
                </Card>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
import {Badge} from "@/components/ui/badge";
import {Card, CardContent} from "@/components/ui/card";
import {Sparkles} from "lucide-vue-next";
</script>
