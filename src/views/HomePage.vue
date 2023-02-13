<template>
    <NavComponent>
        <div class="h-full w-full flex flex-col">
            <div class="w-full flex lg:flex-row 2xs:flex-col py-8">
                <div class="flex flex-col lg:w-1/2 2xs:w-full mt-20 pr-12">
                    <h1 class="2xl:text-8xl xl:text-5xl lg:text-3xl 2xs:text-6xl font-semibold">Lorem ipsum dolor sit amet, consecteture</h1>
                    <p class="2xl:text-2xl xl:text-xl lg:text-lg 2xs:text-xl font-medium text-[#636262] pr-6 mt-6">Lorem ipsum dolor sit amet, consectetur
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
                <div class="lg:w-1/2 2xs:w-full image-stack lg:mt-0 2xs:mt-12 ">
                    <div class="image-stack__item image-stack__item--bottom">
                        <img src="" alt="btm img" class="bg-[#c4c4c4] w-full lg:h-full 2xs:h-[450px]">
                    </div>
                    <div class="image-stack__item image-stack__item--top">
                        <img src="" alt="top img" class="bg-[#9d9d9d] w-[250px] h-[250px]">
                    </div>
                </div>
            </div>

            <div class="flex lg:flex-row 2xs:flex-col mt-20 pb-4 lg:space-y-0 2xs:space-y-10">
                <div class="lg:h-[600px] 2xs:h-content flex flex-col lg:w-1/3 2xs:w-full lg:pr-16 2xs:pr-0">
                    <p class="text-2xl font-bold">Header Text</p>
                    <p class="text-[#636262] mt-4 text-2xl font-medium">Lorem ipsum dolor sit amet, consectetur
                        adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
                </div>
                <div class="lg:h-[600px] 2xs:h-[500px] lg:w-1/3 2xs:w-full">
                    <img src="" class="lg:h-[600px] 2xs:h-[500px] w-full bg-[#c4c4c4]">
                </div>
                <div class="lg:h-[600px] 2xs:h-content flex flex-col lg:w-1/3 2xs:w-full lg:justify-end 2xs:justify-start lg:pl-16 2xs:pl-0">
                    <p class="text-2xl font-bold">Header Text</p>
                    <p class="text-[#636262] mt-4 text-2xl font-medium">Lorem ipsum dolor sit amet, consectetur
                        adipiscing elit,
                        sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
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