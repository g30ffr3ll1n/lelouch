<template>
    <NavComponent>
        <div class="h-full w-full flex flex-col">
            <div class="w-full flex py-8">
                <div class="flex flex-col w-1/2 mt-20 pr-12">
                    <h1 class="text-8xl font-semibold">Lorem ipsum dolor sit amet, consecteture</h1>
                    <p class="text-2xl font-medium text-gray-500 pr-6 mt-6">Lorem ipsum dolor sit amet, consectetur
                        adipiscing elit, sed do eiusmod tempor incididunt
                        ut labore et dolore
                    </p>

                    <div class="flex mt-12 space-x-4">
                        <button class="flex rounded-lg bg-black text-gray-200 px-6 py-3 text-xl font-semibold">
                            Call to Action
                        </button>
                        <button
                            class="flex rounded-lg bg-white text-black border-2 border-black px-6 py-3 text-xl font-semibold">
                            See Workspace
                        </button>
                    </div>
                </div>
                <div class="flex w-1/2 image-stack">
                    <div class="image-stack__item image-stack__item--bottom">
                        <img src="" alt="btm img" class="bg-gray-300 w-full h-full">
                    </div>
                    <div class="image-stack__item image-stack__item--top">
                        <img src="" alt="top img" class="bg-gray-400 w-[250px] h-[250px]">
                    </div>
                </div>
            </div>

            <div class="flex mt-20 pb-4">
                <div class="h-[600px] flex flex-col w-1/3 pr-16">
                    <p class="text-2xl font-bold">Header Text</p>
                    <p class="text-gray-500 mt-4 text-2xl font-medium">Lorem ipsum dolor sit amet, consectetur
                        adipiscing elit,
                        sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
                </div>
                <div class="h-[600px] w-1/3">
                    <img src="" class="h-[600px] w-full bg-gray-300">
                </div>
                <div class="h-[600px] flex flex-col w-1/3 justify-end pl-16">
                    <p class="text-2xl font-bold">Header Text</p>
                    <p class="text-gray-500 mt-4 text-2xl font-medium">Lorem ipsum dolor sit amet, consectetur
                        adipiscing elit,
                        sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
                </div>
            </div>

            <div class="flex xl:flex-row sm:flex-col mt-20 pb-12">
                <div class="h-[700px] w-1/2 pr-16">
                    <img src="" class="h-[700px] bg-gray-300">
                </div>
                <div class="flex flex-col w-1/2 xl:pr-32 h-[700px]">
                    <div class="flex h-1/2"></div>
                    <div class="flex flex-col h-1/2">
                        <p class="text-6xl font-semibold">Lorem ipsum dolor sit amet, consecteture</p>
                        <p class="text-2xl font-medium text-gray-500 mt-6">Lorem ipsum dolor sit amet, consectetur
                            adipiscing elit, sed do eiusmod tempor incididunt
                            ut labore et dolore
                        </p>
                        <div class="mt-12">
                            <button class="flex rounded-lg bg-black text-gray-200 px-6 py-3 text-xl font-semibold">
                                Call to Action
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>

    </NavComponent>

</template>

<script>
import NavComponent from '@/components/NavComponent.vue';

export default {
    name: 'HomePage',
    components: {
        NavComponent
    },
    data: () => ({

    }),
    methods: {

    },
}
</script>

<style>
.image-stack {
  display: grid;
  position: relative; 
  grid-template-columns: repeat(12, 1fr);
}

.image-stack__item--top {
  grid-column: 7 / -1;
  grid-row: 1;
  z-index: 1; 
}

.image-stack__item--bottom {
  grid-row: 1;
  grid-column: 1 / span 8;
  padding-top: 20%; 
}
</style>