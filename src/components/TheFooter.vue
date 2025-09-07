<template>
    <footer class=" bg-gray-800 text-white pt-16 pb-8">
        <div class="container mx-auto px-4">
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-12 mb-12">
                <!-- Clinic Information -->
                <section class="lg:col-span-2">
                    <header class=" flex items-center mb-6">
                        <Icon icon="fa-solid:clinic-medical" class="text-3xl text-pink-500 mr-3" aria-hidden=" true" />
                        <h2 class=" text-2xl font-bold">Glanour Clinic</h2>
                    </header>
                    <p class=" text-gray-400">Premier  cosmetic clinic dedicated ot enhancing your natural beauty with state-of-the treatments and persolized care in Casable.</p>
                    <nav aria-label="Social Media Links">
                        <ul class="flex space-x-4">
                            <li v-for="(item, index) in socialLinks" :key="index">
                                <a href="#" class=" bg-gray-800 hover:bg-pink-600 w-10 h-10 rounded-full flex items-center justify-center transition duration-300" :aria-label="item.label">
                                    <Icon :icon="item.icon" class="text-lg" />
                                </a>
                            </li>
                        </ul>
                    </nav>
                </section>

                <!-- Quick Link -->
                <section>
                    <h3 class=" text-xl font-bold mb-6 relative pb-2 after:content-[''] after:absolute after:left-0 after:bottom-0 after:w-12 after:h-1 after:bg-pink-500">Quick Links</h3>
                    <nav aria-label="Social Media Links">
                        <ul class="space-x-4">
                            <li v-for="(item, index) in quickLinks" :key="index">
                                <a :href="item.href" class="text-gray-400 hover:text-pink-500 transition">
                                    {{ item.text }}
                                </a>
                            </li>
                        </ul>
                    </nav>
                </section>

                <!-- Contact Info -->
                 <address>
                    <h3 class="text-xl font-bold mb-6 relative pb-2 after:content-[''] after:absolute after:left-0 after:bottom-0 after:w-12 after:h-1 after:bg-pink-500">
                        Contact Us
                    </h3>

                    <nav aria-label="Social Media Links">
                        <ul class="flex flex-col gap-4">
                            <li v-for="(item, index) in contactInfo" :key="index" class="flex items-start">
                                <Icon :icon="item.icon" class="text-pink-500 text-xl mt-1 mr-4 flex-shrink-0" />
                                
                                <component
                                :is="item.content.type"
                                v-bind="item.content.props"
                                class="text-gray-400 hover:text-pink-500 transition"
                                >
                                {{ item.content.text }}
                                </component>
                            </li>
                        </ul>
                    </nav>
                </address>
            </div>

            <!-- News letter -->
             <section class=" bg-gray-600 rounded-xl p-8 mb-12" aria-labelledby="newsletter-heading">
                <div class="flex flex-col lg:flex-row items-center justify-between">
                    <div class="mb-6 lg:mb-0 lg:mr-8">
                        <h3 id="newletter-heading" class=" text-xl font-bold mb-2">Subcribe to Our Nesletter</h3>
                        <p class="text-gray-400">Get updates on special offers and beauty tips</p>
                    </div>
                    <form action="" class="flex flex-col sm:flex-row w-full lg:w-auto" aria-label="Nesletter subcription form">
                        <label for="newsletter-email" class="sr-only">Your Email Address</label>
                        <input type="email" id="newsletter-email" placeholder="Your email address" class="px-6 py-3 rounded-full bg-gray-700 text-white focus:outline-none focus:ring-2 focus:ring-pink-500 mb-3 sm:mr-4 w-full">
                         <div>
                            <button type="submit" class=" bg-pink-600 hover:bg-pink-700 text-white px-8 p-3 rounded-full transition shadow-lg w-full md:w-auto whitespace-nowrap" aria-label="Submit contact form">Subscribe</button>
                        </div>
                    </form>                    
                </div>
             </section>
        </div>
        <footer class="pt-8 border-t border-gray-100 flex flex-col md:flex-row justify-between items-center">
            <p class="text-gray-500 text-sm mx-4 mb-4 md:mb-0">
                &copy; {{ currentYear }} Glamour Clinic. All rights reserved. Develop by <a href="https://shamim.deegau.com/" target="_blank" class="hover:text-pink-500">SAMIM-HosseN.</a>
            </p>
            <nav aria-level="Legal Links" class="mr-4">
                <ul class="flex space-x-6">
                    <li v-for="(link, index) in legalLinks" :key="index">
                        <a :href="link.href" class=" text-gray-500 hover:text-pink-500 text-sm transition">{{ link.text }}</a>
                    </li>
                </ul>
            </nav>
        </footer>
    </footer>
</template>

<script setup>
import {computed, ref} from 'vue'
const currentYear = computed(()=>new Date().getFullYear());
const socialLinks = ref([
    {icon:'fa-brands:facebook-f', label: 'Facebook'},
    {icon:'fa-brands:twitter', label: 'Twitter'},
    {icon:'fa-brands:instagram', label: 'Instagram'},
    {icon:'fa-brands:linkedin-in', label: 'Linkedin'},
    {icon:'fa-brands:youtube', label: 'YouTube'},
]);

const quickLinks =ref([
    {text:'Home', href:'#'},
    {text:'About Us', href:'#about'},
    {text:'Our Service', href:'#service'},
    {text:'Our Specialists', href:'#specialists'},
    {text:'Contact Us', href:'#contact'},
    {text:'Appointment', href:'#appointment'},
]);

const contactInfo =ref([
    {
        icon:'material-symbols:location-on',
        content:{
            type:'a',
            props:{
                href:'#',
                target:'_blank',
                rel:'noopener norefferrer',
            },
            text:'IshaKha Beauty Avenue',
        },
    },
    {
        icon:'fa-solid:phone-alt',
        content:{
            type:'a',
            props:{
                href:'#',
            },
            text:'+880 1533-021557',
        },
    },
    {
        icon:'material-symbols:mail',
        content:{
            type:'a',
            props:{
                href:'mailto:ces.shamim.cub@gmail.com',
            },
            text:'ces.shamim.cub@gmail.com',
        },
    },
    {
        icon:'fa-solid:clock',
        content:{
            type:'span',
            props:{},
            text:'Sun - Thu: 9AM - 8PM, Fri : 2PM-9PM',
        },
    },
]);

const legalLinks =ref([
    {text:'Privacy Policy', href:'#'},
    {text:'Terms of Service', href:'#'},
    {text:'Sitemap', href:'#'},
]);
</script>

<style>

</style>