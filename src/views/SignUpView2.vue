<script setup>
import { ref, watch } from "vue";
const firstInputValue = ref("");
const secondInputValue = ref("");
const thirdInputValue = ref("");
const fourthInputValue = ref("");
const secondInput = ref(null);
const thirdInput = ref(null);
const fourthInput = ref(null);

const handleInput = () => {
  secondInput.value.focus();
};
const handleInput2 = () => {
  thirdInput.value.focus();
};
const handleInput3 = () => {
  fourthInput.value.focus();
};

const countdown = ref(60);
watch(countdown, (newValue) => {
  if (newValue > 0) {
    setTimeout(() => {
      countdown.value--;
    }, 1000);
  }
});
</script>

<template>
    <router-link to="/">
        <img class="w-16 mt-12 ml-24 inline-block" src="/src/assets/imgs/gallery/arrow-circle-left-svgrepo-com 3.png" alt="" />
            </router-link>

  <div class="bg-[#EFEFEF] w-7/12 mx-auto h-[662px] mt-28">
    <div class="flex flex-col ">
      <h2 class="font-bold flex text-3xl mt-12 justify-center">შეიყვანეთ ტელეფონის ნომერზე გამოგზავნილი პინკოდი</h2>
      <div class="flex gap-x-20 items-center mt-48 justify-center">
        <input class="border-[1px] border-black w-16 h-16 rounded-md text-center" :maxlength="1" v-model="firstInputValue"
          @input="handleInput" />
        <input class="border-[1px] border-black w-16 h-16 rounded-md text-center" :maxlength="1"
          v-model="secondInputValue" @input="handleInput2" ref="secondInput" />
        <input class="border-[1px] border-black w-16 h-16 rounded-md text-center" :maxlength="1" v-model="thirdInputValue"
          @input="handleInput3" ref="thirdInput" />
        <input class="border-[1px] border-black w-16 h-16 rounded-md text-center" :maxlength="1"
          v-model="fourthInputValue" @input="handleInput4" ref="fourthInput" />
      </div>
      <p class="mt-16 text-2xl flex justify-center">პინკოდის ხელახლა გაგზავნა შესაძლებელია {{ countdown }}</p>
      <div class="flex justify-between mx-24 mt-20">
       <button type="submit"
        class=" w-72 rounded-md bg-white px-3 py-7 text-2xl  text-[#C8C8C8] shadow-gray-600 shadow-md ">გაგზავნა
      </button>  
       <button type="submit" disabled="true"
        class=" w-72 rounded-md bg-[#1C5178] px-3 py-7 text-2xl  text-white shadow-gray-700 shadow-md ">შემდეგი
      </button> 
      </div>
      
    </div>
  </div>
</template>
