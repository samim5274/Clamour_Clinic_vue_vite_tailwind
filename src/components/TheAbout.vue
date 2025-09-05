<template>
    <section id="about" class="py-14 overflow-hidden bg-gradient-to-br from-pink-100 to-purple-100">
        <div class="container mx-auto px-4">
            <article data-aos="fade-up" data-aos-delay="400" class="flex flex-col lg:flex-row items-center gap-12">
                <!-- image section -->
                 <figure class="lg:w-5/12 relative">
                    <div class="relative z-10 rounded-2xl overflow-hidden shadow-2xl w-full max-w-md mx-auto">
                        <img src="https://thumbs.dreamstime.com/b/doctor-office-2425896.jpg?w=768" alt="About Glamour Clicnic" loading="lazy" class="w-full h-auto object-cover aspect-[4/5]">
                        <div class="absolute inset-0 bg-gradient-to-t from-black/40 to-transparent" aria-hidden="true"></div>
                    </div>

                    <!-- Decorative Elements -->
                    <span class="hidden lg:block absolute -bottom-8 -left-8 w-32 h-32 rounded-full bg-pink-500 opacity-20 z-0"></span>
                    <span class="hidden lg:block absolute -top-10 -right-8 w-40 h-40 rounded-full bg-pink-500 opacity-20 z-0"></span>
                 </figure>

                 <div data-aos="fade-up" data-aos-delay="600" class="lg:w-7/12">
                    <header>
                        <h2 id="about-heading" class="text-3xl md:text-4xl font-bold text-gray-800 mb-6">
                            About <span class="text-pink-600">Glamour Clinic</span>
                        </h2>
                        <p class=" text-lg text-gray-600 mb-6">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Dolore, alias necessitatibus voluptatem dolor facilis sunt, dignissimos nulla nihil reprehenderit doloribus vel pariatur fugiat voluptatibus totam. Consequatur, quibusdam iusto, aliquid nostrum veritatis possimus ipsa ad quasi reiciendis repellat minus dignissimos impedit dolores, fugit nulla doloribus nam odio mollitia voluptate non. Explicabo veritatis tempora at aut nihil ad harum nesciunt accusantium unde?</p>
                    </header>

                    <section class="mb-8">
                        <h3 class="text-xl font-semibold text-gray-800 mb-4"> Our Approch</h3>
                        <ul class=" space-y-3">
                            <li v-for="(item, index) in approchItems" :key="index" class="flex items-start">
                                <figure class=" bg-pink-100 p-1 rounded-full mr-3">
                                    <Icon :icon="item.icon" class=" text-pink-600" aria-hidden="true" />
                                </figure>
                                <p class=" text-gray-700">{{ item.text }}</p>
                            </li>
                        </ul>
                    </section>

                    <!-- status section -->
                     <section class="grid grid-cols-2 gap-4 mb-8">
                        <article v-for="(item, index) in status" :key="index" class=" bg-white p-4 rounded-lg shadow-sm flex items-center">
                            <figure class="mr-3">
                                <Icon :icon="item.icon" class="text-pink-500" aria-hidden="true" />
                            </figure>
                            <div>
                                <strong class="text-xl font-bold text-gray-800">{{ item.value }}</strong>
                                <p class="text-sm text-gray-600">{{ item.label }}</p>
                            </div>
                        </article>                        
                     </section>
                     <nav>
                        <a
                            href="#appointment"
                            class="bg-pink-600 hover:bg-pink-700 text-white text-center px-6 py-3 rounded-full inline-block transition shadow-md focus:outline-none focus-within:ring-2 focus:ring-pink-800 focus:ring-offset-2">
                            Meet Our Specialists
                        </a>
                     </nav>
                 </div>
            </article>

            <!-- Mission start -->
             <aside class="mt-20 bg-white rounded-2xl p-8 md:p-12 shadow-lg relative overflow-hidden">
                <span class=" absolute -top-20 -right-20 w-64 h-64 rounded-full bg-pink-500 opacity-40" aria-hidden="true"></span>
                <div class="relative z-10">
                    <h3 class=" text-2xl font-bold text-gray-800 mb-6">Our Mission</h3>
                    <blockquote class=" text-lg text-gray-700 mb-6">
                        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Sunt, vero. Laborum blanditiis libero molestias eligendi culpa, saepe nesciunt molestiae nihil dignissimos ipsam velit veritatis facilis?
                    </blockquote>
                    <figure class="flex items-center">
                        <div class=" w-12 h-12 rounded-full bg-pink-100 flex items-center justify-center mr-4">
                            <Icon icon="fa-solid:user-md" class=" text-pink-600" />
                        </div>
                        <figcaption>
                            <cite class="font-semibold text-gray-800 not-italic">Dr. Sarah Johans</cite>
                            <p>Medical Director & Founder</p>
                        </figcaption>
                    </figure>
                </div>
             </aside>
        </div>
    </section>
</template>

<script setup>
import { ref } from 'vue'

const approchItems = ref([
    {
        icon: 'fa-solid:heart',
        text: 'Personalixed treatment plans tailored to indivisual needs'
    },
    {
        icon: 'fa-solid:user-md',
        text: 'Personalixed treatment plans tailored to indivisual needs'
    },
    {
        icon: 'fa-solid:clinic-medical',
        text: 'Personalixed treatment plans tailored to indivisual needs'
    },
]);

const status = ref([
    {value: '10+', label: 'Years Experince', icon: 'fa-solid:award'},
    {value: '2.5k', label: 'Happy Client', icon: 'fa-solid:heart'},
    {value: '15+', label: 'Expert Doctors', icon: 'fa-solid:user-md'},
    {value: '50+', label: 'Treatmetns', icon: 'fa-solid:clinic-medical'},
]);
</script>

<style>

</style>