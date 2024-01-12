<script setup>
import NavBar from '../components/NavBar.vue'
import { ref } from 'vue'
const card = ref([
    {
        img: 'src/assets/imgs/gallery/image 2 (2).png',
        name: 'მონა ლიზა',
        price: '5000$',
        button: 'ყიდვა'
    },
    {
        img: 'src/assets/imgs/gallery/image 3 (2).png',
        name: 'ქალბატონი ერმინით',
        price: '3500$',
        button: 'ყიდვა',
    },
    {
        img: 'src/assets/imgs/gallery/image 6 (3).png',
        name: 'სალვატორ მუნდი',
        price: '4599$',
        button: 'ყიდვა',
    },
])
const svgs = ref([
    { img: 'src/assets/imgs/cards/Group 35 (1).png' },
    { img: 'src/assets/imgs/cards/Group 35.png' },
])
const timeCheckbox = ref([
    {
        label: 'ბოლოს დამატებული'
    },
    {
        label: 'პირველად დამატებული'
    }
])
const popularityCheckbox = ref([
    {
        label: 'ყველაზე ხშირად ნახვადი '
    },
    {
        label: 'ყველაზე ხშირად ნახვადი '
    }
])
</script>


<template>
    <div class="flex justify-end mt-6">
        <NavBar />
    </div>
    <div>
        <h2 class="text-6xl font-semibold flex justify-center my-16">გალერეა</h2>

        <div class="flex justify-between ">
            <div class="flex flex-col gap-y-12 pl-12 ">
                <div class="mb-3">
                    <div class="relative mb-4 flex w-full flex-wrap items-stretch">
                        <input placeholder="ძებნა" type="search " class="py-1 px-32  border border-gray-700 rounded-sm">
                        <span
                            class=" flex items-center  rounded px-3 py-1.5 text-center text-base font-normal text-neutral-700 dark:text-neutral-200"
                            id="basic-addon2">
                            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor"
                                class="bi bi-search" viewBox="0 0 16 16">
                                <path
                                    d="M11.742 10.344a6.5 6.5 0 1 0-1.397 1.398h-.001q.044.06.098.115l3.85 3.85a1 1 0 0 0 1.415-1.414l-3.85-3.85a1 1 0 0 0-.115-.1zM12 6.5a5.5 5.5 0 1 1-11 0 5.5 5.5 0 0 1 11 0" />
                            </svg>
                        </span>
                    </div>
                </div>
                <!-- <div>
                    <h3>ფასი</h3>
                </div> -->
                <div class="border border-gray-600 rounded-sm">
                    <h2 class="text-lg bg-[#D9D9D9] w-[480px] pl-5 py-2">დრო</h2>

                    <div v-for="item in timeCheckbox" :key="item.index" class="flex items-center mb-4 pl-5 pt-4">
                        <input id="default-checkbox" type="checkbox" value=""
                            class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded ">
                        <label for="default-checkbox" class="ms-2 text-sm font-medium text-gray-900 dark:text-gray-300">{{
                            item.label }}</label>
                    </div>
                </div>
                <div>
                    <div class="border border-gray-600 rounded-sm">
                        <h2 class="text-lg bg-[#D9D9D9] w-[480px] pl-5 py-2">პოპულარული</h2>

                        <div v-for="item in popularityCheckbox" :key="item.index" class="flex items-center mb-4 pl-5 pt-4">
                            <input id="default-checkbox" type="checkbox" value=""
                                class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded ">
                            <label for="default-checkbox"
                                class="ms-2 text-sm font-medium text-gray-900 dark:text-gray-300">{{
                                    item.label }}</label>
                        </div>
                    </div>


                </div>

            </div>

            <div class="flex mx-20 gap-32 justify-end">
                <div v-for="item in card " :key="item.index" class="max-w-sm bg-white rounded-lg ">
                    <a href="#">
                        <img :src="item.img" alt="" />
                    </a>
                    <div class="flex justify-between ">
                        <div class="my-5">
                            <a href="#">
                                <h5 class="mb-4 tracking-tight text-gray-900 ">{{ item.name }}
                                </h5>
                            </a>
                            <p class="mb-4 font-medium text-black">{{ item.price }}</p>
                            <button class="border py-1 px-5 bg-[#1C5178] text-gray-300">{{ item.button }}</button>
                        </div>
                        <div class="flex flex-col gap-y-1 mt-1 ">
                            <div v-for="icon in svgs" :key="icon.index">
                                <img :src="icon.img" alt="">
                            </div>
                        </div>
                    </div>

                </div>
            </div>
        </div>

    </div>
</template>
