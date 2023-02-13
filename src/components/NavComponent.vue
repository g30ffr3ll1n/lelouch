<template>
    <div class="flex flex-col h-full bg-[#ffffff] overflow-y-auto">
        <header class="sticky top-0 z-30 w-full md:px-40 py-4 bg-white sm:px-4 shadow-xl h-20">
            <div class="flex items-center justify-between">
                <a href="#">
                    <span class="text-2xl font-bold text-black">Logo</span>
                </a>
                <div class="flex items-center space-x-1">
                    <ul class="hidden space-x-2 md:inline-flex">
                        <router-link to="/" class="px-4 py-2 font-semibold "
                            active-class="active-route">Home</router-link>
                        <router-link to="/about" class="px-4 py-2 font-semibold "
                            active-class="active-route">About</router-link>
                        <router-link to="/services" class="px-4 py-2 font-semibold "
                            active-class="active-route">Services</router-link>
                        <router-link to="/products" class="px-4 py-2 font-semibold "
                            active-class="active-route">Products</router-link>

                    </ul>
                    <div class="inline-flex md:hidden">
                        <button class="flex-none px-2 ">
                            <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" fill="none" viewBox="0 0 24 24"
                                stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M4 8h16M4 16h16" />
                            </svg>
                            <span class="sr-only">Open Menu</span>
                        </button>
                        <!-- put list item -->
                    </div>
                </div>

                <div>
                    <button class="flex rounded-lg bg-black text-gray-200 px-6 py-3">
                        Call to Action
                    </button>
                </div>
            </div>
        </header>

        <section class="w-full py-4 px-40">
            <slot></slot>
        </section>

        <Footer class="w-full pt-4 pb-12 px-40 footer-bg">

            <FooterComponent></FooterComponent>
        </Footer>
    </div>
</template>

<script>
import { mapActions } from 'vuex'
import FooterComponent from '@/components/FooterComponent.vue';

export default {
    name: 'NavComponent',
    components: {
        FooterComponent
    },
    methods: {
        ...mapActions('auth', {
            logoutUser: 'logout'
        }),
    }
}
</script>

<style>
.active-route {
    @apply text-blue-800;
}

.footer-bg {
    background-image: linear-gradient(#ffffff 30%, #ececec 0%);
}
</style>