<template>
  <div class="w-full flex justify-center">
    <div class="relative mx-auto my-16 w-11/12 z-10">
      <div class="relative font-bold z-30 text-6xl mb-10 text-center lg:text-left">Get in touch</div>
      <div class="absolute top-0 w-full flex justify-center">
      <img draggable=false class="transform -translate-y-24 sm:-translate-y-40 translate-x-0 lg:translate-x-48" src="/contact/leaves.png">
      </div>
      <div class="relative rounded-3xl bg-app-gray-2 flex flex-col-reverse lg:flex-row justify-center lg:justify-end items-center">
        <div class="relative lg:absolute lg:left-0 w-full h-full rounded-3xl flex items-end justify-center lg:justify-start select-none">
          <img
            draggable=false
            class="hidden lg:block lg:absolute lg:left-0 object-cover z-10 w-1/3 h-full rounded-2xl"
            src="/contact/bunchofleaves.png"
          >
          <img
            draggable=false
            class="lg:pl-6 lg:pt-6 object-contain z-20 w-1/2 lg:w-1/4 max-h-full"
            src="/contact/unboggled.png"
          >
        </div>
        <form class="z-30 flex w-full lg:w-2/3 flex-col justify-center pt-8 pb-0 lg:pb-8" @submit.prevent="submit">
          <div class="w-full flex flex-wrap flex-row justify-start items-center px-8">
            <div class="flex flex-col pb-4 lg:pb-0 w-full lg:w-1/2 lg:pr-4">
              <label class="text-xl mb-2">Name & Last Name</label>
              <input
                class="bg-app-gray-1 p-4 text-xl rounded-xl text-app-gray-3 placeholder-app-gray-3 font-bold outline-none border-2 border-transparent focus:border-app-green-1" 
                v-model="form.fullname"
                placeholder="Write your first & last name here"
              />
            </div>
            <div class="flex flex-col w-full lg:w-1/2 lg:pl-4">
              <label class="text-xl font-bold mb-2">Reason:</label>
              <input
                class="bg-app-gray-1 p-4 text-xl rounded-xl text-app-gray-3 placeholder-app-gray-3 font-bold outline-none border-2 border-transparent focus:border-app-green-1" 
                v-model="form.reason"
                placeholder="Write your reason"
              />
            </div>
          </div>
          <div class="flex flex-col mx-8 mt-2">
            <label class="text-xl mb-2">Write your message:</label>
            <textarea
              class="bg-app-gray-1 p-4 text-xl rounded-xl text-app-gray-3 placeholder-app-gray-3 font-bold resize-none outline-none border-2 border-transparent focus:border-app-green-1" 
              v-model="form.message"
              rows=6
              placeholder="Write your message"
            />
          </div>
          <div class="m-6 flex justify-center">
            <button
              type="submit"
              class="px-12 py-2 font-bold text-2xl text-app-green-1 border-4 border-app-green-1 rounded-full focus:outline-none"
            >
              Send message
            </button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import { reactive } from "@nuxtjs/composition-api";

export default {
  setup() {
    const form = reactive({
      fullname: "",
      reason: "",
      message: "",
    });

    function submit(e) {
      console.log(form.fullname, form.reason, form.message);

      // clear form values (tried using e.target.reset(), but it doesn't update reactive form values)
      Object.keys(form).forEach((key, value) => form[key] = "");
    }
    
    return { form, submit }
  },
}
</script>