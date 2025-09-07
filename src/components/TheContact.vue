<template>
    <section class=" py-20 overflow-hidden bg-gradient-to-r from-pink-100 to-purple-100" id="contact">
        <div class="container mx-auto px-4">
            <!-- Section Header -->
            <header class=" text-center mb-16 relative" data-aos="fade-up" data-aos-delay="400">
                <span class=" absolute -top-10 left-1/2 transform -translate-x-1/2 w-20 h-20 rounded-full bg-pink-100 opacity-30 z-0" aria-hidden="true"></span>
                <h2 id="specialist-heading" class=" text-3xl md:text-4xl font-bold text-gray-800 mb-4 relative z-10">Contact <span class=" text-pink-600">Our Clinic</span></h2>
                <p class=" text-lg text-gray-600 max-w-2xl mx-auto relative z-10">
                    Reach out ot schedule your consultation or ask questions about services
                </p>
                <span class=" absolute -bottom-6 ring-1/4 w-16 h-16 rounded-full bg-purple-100 opacity-20 z-0" aria-hidden=" true"></span>
            </header>

            <!-- Main content -->
             <main class=" flex flex-col lg:flex-row gap-12">
                <!-- Contact Info -->
                <aside class="lg:w-2/5">
                    <section class="bg-white rounded-2xl shadow-xl p-8 h-full">
                        <h2 class="text-2xl font-bold text-gray-800 mb-6">Get In Touch</h2>
                        <address class=" space-y-6">
                            <article v-for="(item, index) in contactItems" :key="index" class="flex items-start">
                                <figure class=" bg-pink-100 p-3 rounded-full mr-4 flex-shrink-0">
                                    <Icon :icon="item.icon" class="text-pink-600 text-xl" />
                                </figure>
                                <div>
                                    <h3 class=" font-semibold text-gray-800 mb-1">{{ item.title }}</h3>
                                    <div v-html="item.content" class="text-gray-600"></div>
                                </div>
                            </article>
                        </address>
                        <figure class="mt-8 rounded-xl overflow-hidden shadow-md">
                            <img src="https://smartbd.com/wp-content/uploads/2023/04/call-center-customer-service-tips-scaled-1.jpeg" alt="Glamour Clinic Building" class="w-full h-48 object-cover hover:scale-105 transition-transform duration-500" width="400" height="200" loading="lazy">
                        </figure>
                    </section>
                </aside>

                <!-- Cotnact Form -->
                 <section class="lg:w-3/5">
                    <div class=" bg-white rounded-2xl text-gray-800 p-8 mb-6">
                        <h2 class=" text-2xl font-bold text-gray-800 mb-6">Send Us a Message</h2>
                        <form action="" class=" space-y-6">
                            <fieldset class=" grid grid-cols-1 md:grid-cols-2 gap-6">
                                <div>
                                    <label for="name" class=" block text-gray-700 font-medium mb-2">Full Name</label>
                                    <input type="text" id="name" name="text" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-pink-500 focus:border-transparent" placeholder="Your name" required>
                                </div>
                                <div>
                                    <label for="phone" class=" block text-gray-700 font-medium mb-2">Phone</label>
                                    <input type="tel" id="phone" name="text" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-pink-500 focus:border-transparent" placeholder="+880 1533-021557" required>
                                </div>
                            </fieldset>
                            <div>
                                <label for="email" class=" block text-gray-700 font-medium mb-2">Email</label>
                                <input type="email" id="email" name="text" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-pink-500 focus:border-transparent" placeholder="cse.shamim.cub@gamil.com" required>
                            </div>
                            <div>
                                <label for="service" class=" block text-gray-700 font-medium mb-2">Service Intersed In</label>
                                <select id="service" name="text" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-pink-500 focus:border-transparent" required>
                                    <option selected disabled>-- Select a service --</option>
                                    <option v-for="s in services" :key="s.value" :value="s.value">{{ s.label }}</option>
                                </select>
                            </div>
                            <div>
                                <label for="service" class=" block text-gray-700 font-medium mb-2">Your Message</label>
                                <textarea 
                                id="message" 
                                name="message" 
                                rows="5" 
                                placeholder="Tell us about you r concers or question"
                                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-pink-500 focus:border-transparent" required>
                                </textarea>
                            </div>
                            <div>
                                <button type="submit" class=" bg-pink-600 hover:bg-pink-700 text-white px-8 p-3 rounded-full transition shadow-lg w-full md:w-auto" aria-label="Submit contact form">Send Message</button>
                            </div>
                        </form>
                    </div>
                 </section>
             </main>

             <!-- Google Map -->
            <figure class="mt-16 bg-white rounded-2xl shadow-xl overflow-hidden">
                <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d1824.2553927783913!2d90.40002670321334!3d23.871499700000015!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3755c43ae707319d%3A0x544888469a8dbf39!2sHouse%2002%20Road%20No%2011%2C%20Dhaka%201230!5e0!3m2!1sen!2sbd!4v1757229390083!5m2!1sen!2sbd" width="100%" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade" title="Clinic Locaion Map" class="rounded-2xl" aria-label="Map Showing clicnic locaion"></iframe>
            </figure>
        </div>
    </section> 
</template>

<script setup>
import {ref} from 'vue'
const contactItems = ref([
    {
        icon:'fa-solid:map-marker-alt',
        title:'Our Locaion',
        content:'<p>Beauty Avenue, Medical Districkt <br> Casblance 11564, Morocco.</p>',
    },
    {
        icon:'fa-solid:phone-alt',
        title:'Phone',
        content:'<p><a href="tel:+8801533021557" class="text-pink-600"> +880 1533-021557</a><br> Emergency: <a href="tel:+8801533021557" class="text-pink-600"> +880 1533-021557</a></p>',
    },
    {
        icon:'fa-solid:envelope',
        title:'Email',
        content:'<p><a href="mailto:ces.shamim.cub@gmail.com" class="text-pink-600">mailto: ces.shamim.cub@gmail.com</a><br> Emergency: <a href="mailto:ces.shamim.cub@gmail.com" class="text-pink-600"> mailto:ces.shamim.cub@gmail.com</a> </p>',
    },
    {
        icon:'fa-solid:clock',
        title:'Working Hours',
        content:'<p> Sunday - Thursday: 9:00 AM - 8:00 PM<br>  Friday : 2:00 PM - 9:00 PM<br> Saturday: Closed </p>',
    },
]);

const services = ref([
    {value: "botox", label:'Botox Treatmetns'},
    {value: "fillers", label:'Dermal Fillers'},
    {value: "laser", label:'Laser Therapy'},
    {value: "facelift", label:'Non-Surgical Facelift'},
    {value: "other", label:'Others'},
]);
</script>

<style>

</style>