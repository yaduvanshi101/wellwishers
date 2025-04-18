<script setup lang="ts">
import {
    Globe,
    Smartphone,
    Cloud,
    Cpu,
    PenTool,
    Info,
    Briefcase,
    Mail,
    Linkedin,
    AtSign,
} from "lucide-vue-next";

interface Footerlink {
    title: string;
    links?: {
        name: string;
        icon?: any;
        href?: string;
    }[];
}

const sections: Footerlink[] = [
    {
        title: "Services",
        links: [
            {name: "Web Development", icon: Globe},
            {name: "Mobile Apps", icon: Smartphone},
            {name: "Salesforce", icon: Cloud},
            {name: "AI Solutions", icon: Cpu},
            {name: "Design Services", icon: PenTool},
        ],
    },
    {
        title: "Company",
        links: [
            {name: "About Us", icon: Info},
            {name: "Our Work", icon: Briefcase},
            {name: "Contact", icon: Mail},
        ],
    },
    {
        title: "Connect",
        links: [
            {
                name: "LinkedIn",
                icon: Linkedin,
                href: "https://www.linkedin.com/in/rohit-singh-669896219/",
            },
            {
                name: "Email Us",
                href: "mailto:wellwishersolution@gmail.com",
                icon: AtSign,
            },
        ],
    },
];
</script>

<template>
    <section
        id="footer"
        class="relative flex items-center bg-primary py-8 md:py-16 lg:py-24 w-full text-secondary scroll-mt-24"
    >
        <div class="mx-auto px-4 md:px-6 lg:px-8 container">
            <footer>
                <div class="gap-8 grid grid-cols-2 lg:grid-cols-6">
                    <div class="col-span-2 mb-8 lg:mb-0">
                        <div class="flex items-center space-x-2 mb-4">
                            <a href="#hero" class="font-bold text-xl">
                                <img
                                    src="/assets/logo.png"
                                    alt="Logo"
                                    class="invert h-12"
                                />
                            </a>
                        </div>
                        <p class="font-bold">
                            Craft the future with WellWishers.
                        </p>
                    </div>
                    <div
                        v-for="(section, sectionIdx) in sections"
                        :key="sectionIdx"
                    >
                        <h3 class="mb-4 font-bold">{{ section.title }}</h3>
                        <ul class="space-y-4">
                            <li
                                v-for="(link, linkIdx) in section.links"
                                :key="linkIdx"
                                class="group font-medium"
                            >
                                <a
                                    class="flex items-center gap-2"
                                    :href="link.href"
                                >
                                    <component
                                        :is="link.icon"
                                        class="group-hover:opacity-100 size-4 transition-opacity"
                                    />
                                    {{ link.name }}
                                </a>
                            </li>
                        </ul>
                    </div>
                </div>
                <div
                    class="flex md:flex-row flex-col md:justify-between items-center md:items-center gap-4 mt-24 pt-8 border-t font-medium text-sm"
                >
                    <p>2024 Your Company. All rights reserved.</p>
                    <ul class="flex gap-4">
                        <li class="underline">
                            <a href="#" class="flex items-center gap-1">
                                <ScrollText class="size-4" />
                                Terms of Service
                            </a>
                        </li>
                        <li class="underline">
                            <a href="#" class="flex items-center gap-1">
                                <Shield class="size-4" />
                                Privacy Policy
                            </a>
                        </li>
                    </ul>
                </div>
            </footer>
        </div>
    </section>
</template>
