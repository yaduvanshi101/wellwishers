<script setup lang="ts">
import {Badge} from "@/components/ui/badge";
import {Avatar, AvatarFallback, AvatarImage} from "@/components/ui/avatar";
import {Users} from "lucide-vue-next";

interface Person {
    id: number;
    name: string;
    initials: string;
    role: string;
    avatar: string;
    department: string;
    bio: string;
    skills: string[];
}

const people: Person[] = [
    {
        id: 1,
        name: "Rohit Singh",
        initials: "R",
        role: "Founder & CEO",
        avatar: "/assets/rohit.jpg",
        department: "Managing",
        bio: "Visionary leader with a passion for technology and innovation.",
        skills: ["AWS", "PHP", "MySQL", "Java", "Python"],
    },
    {
        id: 2,
        name: "Himanshu",
        initials: "h",
        role: "UI/UX Designer",
        avatar: "/assets/himanshu.jpg",
        department: "Design",
        bio: "Creative UI/UX Designer with a focus on intuitive user interfaces.",
        skills: ["Figma", "Adobe XD", "Prototyping"],
    },
    {
        id: 3,
        name: "Nitish",
        initials: "N",
        role: "Technical Staff",
        avatar: "/assets/nitish.jpg",
        department: "Development",
        bio: "Full Stack Developer with expertise in backend and frontend technologies.",
        skills: ["Node.js", "Python", "React", "Javascript"],
    },
    {
        id: 4,
        name: "Siddhansh",
        initials: "S",
        role: "Technical Staff",
        avatar: "/assets/siddhansh.jpg",
        department: "Development",
        bio: "Software Engineer with a knack for solving complex problems.",
        skills: ["Salesforce", "Java", "C++", "MySQL", "JavaScript"],
    },
];
</script>

<template>
    <section
        id="team"
        class="relative flex items-center bg-white py-8 md:py-16 lg:py-24 w-full"
    >
        <div class="mx-auto px-4 md:px-6 lg:px-8 container">
            <!-- Content -->
            <div class="relative">
                <!-- Header -->
                <div class="space-y-4 mb-12 text-center">
                    <Badge variant="outline" class="mb-4">
                        <Users class="mr-2 size-4" />
                        Team
                    </Badge>
                    <h2
                        class="font-bold text-3xl sm:text-4xl md:text-5xl tracking-tighter"
                    >
                        Our Team
                    </h2>
                    <p
                        class="mx-auto max-w-3xl text-muted-foreground lg:text-base/relaxed md:text-xl/relaxed xl:text-xl/relaxed"
                    >
                        A diverse team of experts who work with passion to
                        develop innovative solutions for our customers.
                    </p>
                </div>

                <!-- Team Grid -->
                <div
                    class="gap-8 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4"
                >
                    <div
                        v-for="person in people"
                        :key="person.id"
                        class="group relative"
                    >
                        <div
                            class="relative bg-white hover:shadow-lg p-6 border rounded-lg transition-all duration-300"
                        >
                            <!-- Avatar with Hover Effect -->
                            <div class="relative flex justify-center mb-4">
                                <Avatar
                                    class="border-4 border-background size-24 group-hover:scale-110 transition-transform duration-300"
                                >
                                    <AvatarImage
                                        :src="person.avatar"
                                        :alt="person.name"
                                    />
                                    <AvatarFallback>{{
                                        person.initials
                                    }}</AvatarFallback>
                                </Avatar>
                            </div>

                            <div class="space-y-2 text-center">
                                <h3 class="font-semibold">{{ person.name }}</h3>
                                <p class="text-muted-foreground text-sm">
                                    {{ person.role }}
                                </p>

                                <div
                                    class="flex flex-wrap justify-center gap-1 mt-2"
                                >
                                    <Badge
                                        v-for="skill in person.skills.slice(
                                            0,
                                            2
                                        )"
                                        :key="skill"
                                        variant="secondary"
                                        class="text-xs"
                                    >
                                        {{ skill }}
                                    </Badge>
                                </div>
                            </div>

                            <div
                                class="z-10 absolute inset-0 flex justify-center items-center opacity-0 group-hover:opacity-100 transition-opacity"
                            >
                                <div
                                    class="flex flex-col justify-center bg-black/80 backdrop-blur-sm p-6 rounded-lg w-full h-full text-white"
                                >
                                    <p
                                        class="text-sm text-center leading-relaxed"
                                    >
                                        {{ person.bio }}
                                    </p>
                                    <div
                                        class="flex flex-wrap justify-center gap-1 mt-4"
                                    >
                                        <Badge
                                            v-for="skill in person.skills"
                                            :key="skill"
                                            variant="outline"
                                            class="border-white/20 text-white text-xs"
                                        >
                                            {{ skill }}
                                        </Badge>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>
