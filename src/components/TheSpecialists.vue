<template>
    <section class=" py-20 overflow-hidden bg-gradient-to-r from-pink-100 to-purple-100" id="specialists">
        <div class="container mx-auto px-4">
            <!-- Section Header -->
            <header class=" text-center mb-16 relative" data-aos="fade-up" data-aos-delay="400">
                <span class=" absolute -top-10 left-1/2 transform -translate-x-1/2 w-20 h-20 rounded-full bg-pink-100 opacity-30 z-0" aria-hidden="true"></span>
                <h2 id="specialist-heading" class=" text-3xl md:text-4xl font-bold text-gray-800 mb-4 relative z-10">Meet Our <span class=" text-pink-600">Expert Team</span></h2>
                <p class=" text-lg text-gray-600 max-w-2xl mx-auto relative z-10">
                    Our board-certified specilists comnine medical expertise with artistic vision.
                </p>
                <span class=" absolute -bottom-6 ring-1/4 w-16 h-16 rounded-full bg-purple-100 opacity-20 z-0" aria-hidden=" true"></span>
            </header>

            <!-- Specilist Gridn -->
            <ul data-aos="fade-up" data-aos-delay="500" class=" grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 mb-16">
                <li v-for="doctor in specialists" :key="doctor.id" class="group relative">
                    <article class=" bg-white rounded-xl shadow-lg overflow-hidden hover:shadow-xl transition-all duration-300 h-full">
                        <figure class=" relative h-80 overflow-hidden">                            
                            <img :src="doctor.image" :alt="doctor.name" class=" w-full h-full object-cover transition-transform duration-500 group-hover:scale-105" loading="lazy">

                            <span class=" absolute inset-0 bg-gradient-to-t from-back/60 to-transparent" aria-hidden="true"></span>

                            <aside class=" absolute top-4 right-4 bg-white/90 px-3 py-1 rounded-full flex items-center shadow-sm" :aria-label="`Rating: ${doctor.rating} stars`">
                                <Icon
                                    v-for="i in 5"
                                    :key="i"
                                    :icon="i <= doctor.rating ? 'mdi:star' : 'mdi:star-outline'"
                                    class="text-yellow-400 inline"/>
                                <span class=" ml-1 text-sm font-medium">{{ doctor.rating }}</span>
                            </aside>
                        </figure>

                        <div class="p-6 relative -mt-10">
                            <div class="bg-pink-50 rounded-lg shadow-md p-6">
                                <header>
                                    <h3 class="text-xl font-bold text-gray-800 mb-1">{{ doctor.name }}</h3>
                                    <p class="text-pink-600 font-medium mb-3">{{ doctor.role }}</p>
                                </header>
                                <p class=" text-gray-600 mb-4">{{ doctor.bio }}</p>
                                <ul class="flex flex-wrap gap-2 mb-4">
                                    <li v-for="(spec, i) in doctor.specialities" :key="i">
                                        <span class=" bg-pink-50 text-pink-600 text-xs font-medium px-3 py-1 rounded-full">{{ spec }}</span>
                                    </li>
                                </ul>

                                <figure class=" absolute -top-6 left-6 bg-pink-600 text-white p-3 rounded-full shadow-lg" aria-hidden=" true">
                                    <Icon icon="mdi:format-quote-open" class=" text-lg" />
                                </figure>
                            </div>
                        </div>
                    </article>
                </li>
            </ul>

            <!-- CTA Section -->
             <aside class=" bg-gradient-to-r from-pink-100 to-purple-100 rounded-2xl p-8 md:p-12 text-center relative overflow-hidden" data-aos="fade-up" data-aos-delay="500">
                
                <span class="absolute -top-20 -left-20 w-32 h-32 rounded-full bg-pink-300 opacity-20" aria-hidden=" true"></span>
                <span class="absolute -bottom-20 -right-20 w-60 h-60 rounded-full bg-purple-300 opacity-20" aria-hidden=" true"></span>

                <div class=" relative z-10">
                    <h3 class=" text-2xl md:text-3xl font-bold text-gray-800 mb-6">
                        Ready to Consult With Our Specialists?
                    </h3>
                    <p class=" text-lg text-gray-600 mb-8 max-w-2xl mx-auto">
                        Book a personalixed consultation to discuess you r aesthetic goals and treatment options.
                    </p>
                    <nav class="flex flex-col sm:flex-row justify-center gap-4">
                        <a
                            href="#appointment"
                            class="bg-pink-600 hover:bg-pink-700 text-white text-center px-6 py-3 rounded-full inline-block transition shadow-md focus:outline-none focus-within:ring-2 focus:ring-pink-800 focus:ring-offset-2">
                            Book Consultation
                        </a>
                        <a href="#Contact" class="border border-pink-600 text-pink-600 hover:bg-pink-50 px-8 py-3 rounded-full transition focus:outline-none focus-within:ring-2 focus:ring-pink-600 focus:ring-offset-2" aria-label="Contact Us">
                            Contact Us
                        </a>
                    </nav>
                </div>
             </aside>
        </div> 
    </section>
</template>

<script setup>
import Image1 from '/img/doctor-1.jpg';
import Image2 from '/img/doctor-2.jpg';
import Image3 from '/img/doctor-3.jpg';
import { ref } from 'vue';

const specialists = ref([
    {
        id:1,
        name: 'Dr. Anne Johson',
        role: 'Plastic Surgeon',
        image: Image1,
        rating: 5.0,
        bio: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Illum, fugiat.",
        specialities: ['Facelifts', 'Rhinoplasty', 'Blepharoplasty']
    },
    {
        id:2,
        name: 'Dr. Elena Rofrigurez',
        role: 'Aesthetic Physician',
        image: Image2,
        rating: 4.0,
        bio: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Illum, fugiat.",
        specialities: ['CoolSculpting', 'Ultherapy', 'Thread Lifts']
    },
    {
        id:3,
        name: 'Dr. Michael Chen',
        role: 'Dermatologist',
        image: Image3,
        rating: 4.5,
        bio: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Illum, fugiat.",
        specialities: ['Laser treatments', 'Botox', 'Fillers']
    }
]);
</script>


<style>

</style>