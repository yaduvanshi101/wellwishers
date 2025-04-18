<template>
    <section
        id="hero"
        class="relative flex items-center bg-white py-8 md:py-16 lg:py-24 w-full scroll-mt-24"
    >
        <div class="mx-auto px-4 md:px-6 lg:px-8 container">
            <div class="items-center gap-8 lg:gap-16 grid lg:grid-cols-2">
                <div
                    class="flex flex-col items-center lg:items-start space-y-6 lg:text-left text-center"
                >
                    <h1
                        class="font-bold text-4xl lg:text-6xl xl:text-7xl text-pretty tracking-tight"
                    >
                        Crafting Digital Experiences with
                        <span class="text-primary">Wellwishers</span>
                    </h1>
                    <p
                        class="max-w-[42rem] font-medium text-muted-foreground text-lg lg:text-xl"
                    >
                        Discover our comprehensive suite of digital services.
                        From web development to digital marketing, we deliver
                        solutions optimized for performance and business growth.
                    </p>
                    <p
                        class="max-w-[42rem] text-muted-foreground text-lg lg:text-xl"
                    >
                        Built by experts for businesses of all sizes. With a
                        focus on quality and results, we're ready to elevate
                        your digital presence to the next level.
                    </p>
                    <div
                        class="flex sm:flex-row flex-col justify-center lg:justify-start gap-3 w-full"
                    >
                        <Button
                            size="lg"
                            class="group w-full sm:w-auto"
                            onclick="document.getElementById('services').scrollIntoView({ behavior: 'smooth' })"
                        >
                            Our Services
                            <ArrowRight
                                class="ml-2 size-4 transition-transform group-hover:translate-x-1.5 duration-300"
                            />
                        </Button>
                    </div>
                </div>
                <div class="relative">
                    <div class="relative rounded-xl overflow-hidden">
                        <img
                            src="https://images.unsplash.com/photo-1551434678-e076c223a692?q=80&w=2070&auto=format&fit=crop"
                            alt="Vue Components Preview"
                            class="shadow-2xl w-full object-cover aspect-[16/10] hover:scale-[1.02] transition-all duration-300"
                        />
                        <div
                            class="absolute inset-0 rounded-xl ring-1 ring-black/10 ring-inset"
                        ></div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
import {ArrowRight} from "lucide-vue-next";
import {Button} from "@/components/ui/button";
</script>
