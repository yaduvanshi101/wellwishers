<script setup lang="ts">
import {
    Globe,
    TrendingUp,
    Cloud,
    Cpu,
    PenTool,
    HeartHandshake,
} from "lucide-vue-next";

const features = [
    {
        title: "Web & Mobile Development",
        description:
            "Responsive, high-performance websites and mobile applications built with cutting-edge technologies for seamless user experiences across all devices.",
        icon: Globe,
    },
    {
        title: "Salesforce Solutions",
        description:
            "Custom Salesforce implementations and integrations that streamline your business processes, enhance productivity, and drive growth.",
        icon: Cloud,
    },
    {
        title: "AI & Machine Learning",
        description:
            "Intelligent solutions that leverage the latest AI technologies to automate processes, extract insights from data, and create smarter applications.",
        icon: Cpu,
    },
    {
        title: "Creative UI/UX Services",
        description:
            "Stunning visual designs that communicate your brand story, captivate your audience, and elevate your digital presence.",
        icon: PenTool,
    },
    {
        title: "Digital Marketing Expertise",
        description:
            "Data-driven marketing strategies that boost your online presence, engage target audiences, and convert visitors into loyal customers.",
        icon: TrendingUp,
    },
    {
        title: "End-to-End Support",
        description:
            "Comprehensive partnership from concept to deployment and beyond, ensuring your digital solutions continue to deliver long-term value.",
        icon: HeartHandshake,
    },
];
</script>

<template>
    <section
        id="features"
        class="relative flex items-center bg-white py-8 md:py-16 lg:py-24 w-full"
    >
        <div class="mx-auto px-4 md:px-6 lg:px-8 container">
            <!-- Header -->
            <div class="mx-auto mb-12 max-w-3xl text-center">
                <p class="mb-4 font-medium text-primary text-sm">
                    Core Features
                </p>
                <h2 class="font-bold text-4xl sm:text-5xl tracking-tighter">
                    Our Core <span class="text-primary">Competencies</span>
                </h2>
                <p class="mt-4 text-muted-foreground text-lg">
                    Discover the powerful features that make our platform stand
                    out from the rest
                </p>
            </div>

            <!-- Features Grid -->
            <div class="gap-8 grid md:grid-cols-2 lg:grid-cols-3 mt-16">
                <div
                    v-for="(feature, idx) in features"
                    :key="idx"
                    class="group relative bg-white shadow-sm hover:shadow-xl p-8 rounded-2xl transition-all duration-300"
                >
                    <!-- Icon Container -->
                    <div class="mb-6">
                        <div
                            class="inline-flex justify-center items-center bg-primary/10 group-hover:bg-primary rounded-xl size-14 transition-colors duration-300"
                        >
                            <component
                                :is="feature.icon"
                                class="size-7 text-primary group-hover:text-white transition-colors duration-300"
                            />
                        </div>
                    </div>

                    <!-- Content -->
                    <div>
                        <h3 class="mb-3 font-semibold text-xl">
                            {{ feature.title }}
                        </h3>
                        <p class="text-muted-foreground">
                            {{ feature.description }}
                        </p>
                    </div>

                    <!-- Hover Effect Line -->
                    <div
                        class="right-0 bottom-0 left-0 absolute bg-gradient-to-r from-primary to-primary/60 h-1 scale-x-0 group-hover:scale-x-100 transition-transform duration-300 transform"
                    />
                </div>
            </div>
        </div>
    </section>
</template>
