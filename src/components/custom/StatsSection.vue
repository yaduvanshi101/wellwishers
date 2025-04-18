<script setup lang="ts">
import {ref, onMounted} from "vue";
import {Badge} from "@/components/ui/badge";
import {Card} from "@/components/ui/card";
import {Avatar, AvatarImage, AvatarFallback} from "@/components/ui/avatar";
import {ChartBar, Users, Building2, Trophy, Star} from "lucide-vue-next";

interface Stat {
    label: string;
    value: number;
    icon: any;
    suffix?: string;
    decimals: number;
}
const statsData: Stat[] = [
    {
        label: "Completed Projects",
        value: 25,
        icon: Users,
        suffix: "+",
        decimals: 0,
    },
    {
        label: "Satisfied Clients",
        value: 15,
        icon: Building2,
        suffix: "+",
        decimals: 0,
    },
    {
        label: "On-time Delivery",
        value: 98.5,
        icon: Trophy,
        decimals: 1,
        suffix: "%",
    },
    {
        label: "Client Satisfaction",
        value: 4.8,
        icon: Star,
        decimals: 1,
        suffix: "/5",
    },
];

const stats = ref(
    statsData.map((stat) => ({
        ...stat,
        displayValue: "0",
    }))
);

const animateValue = (stat: Stat, index: number) => {
    const duration = 1500; // 2 seconds
    const steps = 60;
    const stepDuration = duration / steps;
    let currentStep = 0;

    const interval = setInterval(() => {
        currentStep++;
        const progress = currentStep / steps;
        const easedProgress = 1 - Math.pow(1 - progress, 3); // Cubic easing

        const currentValue = stat.value * easedProgress;
        stats.value[index].displayValue = currentValue.toFixed(stat.decimals);

        if (currentStep >= steps) {
            clearInterval(interval);
            stats.value[index].displayValue = stat.value.toFixed(stat.decimals);
        }
    }, stepDuration);
};

onMounted(() => {
    stats.value.forEach((stat, index) => {
        setTimeout(() => {
            animateValue(stat, index);
        }, index * 200); // Stagger the animations
    });
});

const testimonial = {
    quote: "This platform has transformed how we handle our business operations. The statistics speak for themselves - it's been an incredible journey.",
    author: "Rohit Singh",
    role: "CEO at WellWishers",
    avatar: "https://shadcnblocks-vue.com/avatars/sarah-johnson.jpg",
    initials: "RS",
};
</script>

<template>
    <section
        id="stats"
        class="relative flex items-center bg-white py-8 md:py-16 lg:py-24 w-full scroll-mt-24"
    >
        <div class="mx-auto px-4 md:px-6 lg:px-8 container">
            <!-- Header -->
            <div class="space-y-4 mb-12 text-center">
                <Badge variant="outline" class="mb-4">
                    <ChartBar class="mr-2 size-4" />
                    Our Impact
                </Badge>
                <h2
                    class="font-bold text-3xl md:text-4xl lg:text-5xl tracking-tight"
                >
                    Trusted by thousands of customers worldwide
                </h2>
                <p class="mx-auto max-w-2xl text-muted-foreground md:text-lg">
                    We're proud of our numbers and the trust our customers place
                    in us
                </p>
            </div>

            <!-- Stats Grid -->
            <div class="gap-8 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4">
                <Card
                    v-for="stat in stats"
                    :key="stat.label"
                    class="p-6 hover:border-primary text-center transition-all duration-300"
                >
                    <component
                        :is="stat.icon"
                        class="mx-auto mb-4 size-8 text-primary"
                    />
                    <div class="space-y-2">
                        <h3 class="font-bold text-3xl tracking-tight">
                            {{ stat.displayValue }}{{ stat.suffix }}
                        </h3>
                        <p class="text-muted-foreground text-sm">
                            {{ stat.label }}
                        </p>
                    </div>
                </Card>
            </div>

            <!-- Testimonial -->
            <div class="mt-16 text-center">
                <blockquote class="mx-auto max-w-3xl">
                    <p class="font-medium text-muted-foreground text-xl italic">
                        "{{ testimonial.quote }}"
                    </p>
                    <footer class="mt-4">
                        <div class="flex justify-center items-center gap-2">
                            <Avatar>
                                <AvatarImage
                                    :src="testimonial.avatar"
                                    :alt="testimonial.author"
                                />
                                <AvatarFallback>{{
                                    testimonial.initials
                                }}</AvatarFallback>
                            </Avatar>
                            <div class="text-left">
                                <p class="font-semibold">
                                    {{ testimonial.author }}
                                </p>
                                <p class="text-muted-foreground text-sm">
                                    {{ testimonial.role }}
                                </p>
                            </div>
                        </div>
                    </footer>
                </blockquote>
            </div>
        </div>
    </section>
</template>
