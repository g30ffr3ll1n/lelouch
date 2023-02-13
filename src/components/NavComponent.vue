<template>
    <div class="flex flex-col h-full bg-[#ffffff] overflow-y-auto">
        <header class="sticky top-0 z-30 w-full px-4 md:px-20 lg:px-40 py-8 bg-white sm:px-4 h-32">
            <div class="bg-white">
                <nav class=" container mx-auto lg:flex lg:justify-between lg:items-center ">
                    <div class=" flex items-center justify-between">
                        <router-link to="/" class="text-3xl font-bold text-black">
                            Logo
                        </router-link>
                        <!-- Mobile menu button -->
                        <div @click="toggleNav" class="flex lg:hidden">
                            <button type="button"
                                class=" text-gray-600 hover:text-black focus:outline-none focus:text-black ">
                                <svg viewBox="0 0 24 24" class="w-6 h-6 fill-current">
                                    <path fill-rule="evenodd"
                                        d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z">
                                    </path>
                                </svg>
                            </button>
                        </div>
                    </div>

                    <!-- Mobile Menu open: "block", Menu closed: "hidden" -->
                    <ul :class="showMenu ? 'flex' : 'hidden'"
                        class=" flex-col mt-8 space-y-4 lg:flex lg:space-y-0 lg:flex-row lg:items-center lg:space-x-10 lg:mt-0 ">
                        <router-link to="/" class="px-4 py-2 font-semibold text-base lg:text-xl text-[#636262]"
                            active-class="active-route">Home</router-link>
                        <router-link to="/about" class="px-4 py-2 font-semibold text-base lg:text-xl text-[#636262]"
                            active-class="active-route">About</router-link>
                        <router-link to="/services" class="px-4 py-2 font-semibold text-base lg:text-xl text-[#636262]"
                            active-class="active-route">Services</router-link>
                        <router-link to="/products" class="px-4 py-2 font-semibold text-base lg:text-xl text-[#636262]"
                            active-class="active-route">Products</router-link>
                    </ul>

                    <div class="hidden lg:flex">
                        <button class="flex rounded-lg bg-black text-gray-200 px-6 py-3">
                            Call to Action
                        </button>
                    </div>
                </nav>
            </div>
        </header>

        <section class="w-full py-4 px-4 md:px-20 lg:px-40">
            <slot></slot>
        </section>

        <Footer class="w-full pt-4 pb-12 px-4 md:px-20 lg:px-40 footer-bg">

            <FooterComponent></FooterComponent>
        </Footer>
    </div>

</template>

<script>
import { ref } from 'vue';
import { mapActions } from 'vuex'
import FooterComponent from '@/components/FooterComponent.vue';

export default {
    setup() {
        let showMenu = ref(false);
        const toggleNav = () => (showMenu.value = !showMenu.value);
        return { showMenu, toggleNav };
    },
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
    @apply text-black !important;
}

.footer-bg {
    background-image: linear-gradient(#ffffff 30%, #ececec 0%);
}
</style>