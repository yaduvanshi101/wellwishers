<template>
    <section
        id="contact"
        class="relative flex items-center bg-white py-8 md:py-16 lg:py-24 w-full scroll-mt-24"
    >
        <div class="mx-auto px-4 md:px-6 lg:px-8 container">
            <div class="mb-14">
                <span class="font-semibold text-sm">Reach Us</span>
                <h1
                    class="mt-1 mb-3 font-semibold text-3xl md:text-4xl text-balance"
                >
                    Speak with Our Friendly Team
                </h1>
                <p class="text-muted-foreground text-lg">
                    We&apos;d love to assist you. Connect with us.
                </p>
            </div>
            <div class="gap-10 grid md:grid-cols-3">
                <div>
                    <span
                        class="flex flex-col justify-center items-center bg-accent mb-3 rounded-full size-12"
                    >
                        <Mail class="w-auto h-6" />
                    </span>
                    <p class="mb-2 font-semibold text-lg">Email Us</p>
                    <p class="mb-3 text-muted-foreground">
                        Our team is ready to assist.
                    </p>
                    <a
                        href="mailto:wellwishersolution@gmail.com"
                        class="font-semibold hover:underline"
                    >
                        wellwishersolution@gmail.com
                    </a>
                </div>
                <div>
                    <span
                        class="flex flex-col justify-center items-center bg-accent mb-3 rounded-full size-12"
                    >
                        <MapPin class="w-auto h-6" />
                    </span>
                    <p class="mb-2 font-semibold text-lg">Visit Us</p>
                    <p class="mb-3 text-muted-foreground">
                        Drop by our office for a chat.
                    </p>
                    <a
                        href="https://www.google.com/maps/search/?api=1&query=Maholi+Road,+Mathura,+Uttar+Pradesh,+India"
                        target="_blank"
                        rel="noopener noreferrer"
                        class="font-semibold hover:underline"
                    >
                        Maholi Road, Mathura, Uttar Pradesh, India
                    </a>
                </div>
                <div>
                    <span
                        class="flex flex-col justify-center items-center bg-accent mb-3 rounded-full size-12"
                    >
                        <Phone class="w-auto h-6" />
                    </span>
                    <p class="mb-2 font-semibold text-lg">Call Us</p>
                    <p class="mb-3 text-muted-foreground">
                        We&apos;re available Mon-Fri, 10am-6pm.
                    </p>
                    <a
                        href="tel:+918171732534"
                        class="font-semibold hover:underline"
                    >
                        +91 817 173 2534
                    </a>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
import {Mail, MapPin, Phone} from "lucide-vue-next";
</script>

<style scoped></style>
