<template>
  <div class="w-9/10">
    <h3
      class="text-2xl lg:text-4xl font-semibold mb-3 lg:mb-0 text-left tracking-wide"
    >
      Our Packages
    </h3>
    <ul
      class="hidden lg:flex text-sm list-none flex-no-wrap justify-end space-x-12 mr-2 mb-3"
    >
      <li>extra</li>
      <li>Figma</li>
      <li class="text-app-green-1 underline">e-commerce</li>
      <li>Basic</li>
    </ul>

    <div class="w-full lg:rounded-2xl lg:shadow-2xl overflow-x-auto">
      <div class="w-full flex">
        <div
          v-for="(item, id) in Packages"
          :key="id"
          class="package px-6 py-4 flex lg:min-w-0 flex-col items-center rounded-3xl lg:rounded-none mx-2 lg:m-0 border-r-2 bg-app-gray-2 min-w-3/4 text-sm border-app-gray-1 shadow-2xl lg:shadow-none h-auto"
        >
          <img class="my-4" :src="'/packages/' + item.img" alt="pack" />
          <!-- <img src="/packages/Edit4.png" alt=""> -->
          <h4 class="text-xl mb-2 font-medium">{{ item.package }}</h4>
          <p class="mb-4">{{ item.desc }}</p>
          <p><span class="font-bold">3</span> App pages</p>
          <p><span class="font-bold">5</span> Stock images</p>
          <p><span class="font-bold">2</span> Design revision</p>
          <p><span class="font-bold">1</span> Development revision</p>
          <p>Unlimited Contact</p>
          <p class="mt-4">
            <span class="mr-2 text-sm line-through"
              >${{ item.slashedPrice }}</span
            >
            <span class="text-app-green-1 text-xl font-medium"
              >${{ item.price }}</span
            >
          </p>
          <ButtonComp />
          <p class="mt-2">
            Edit request? <span class="font-medium">ContactUs</span>
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import buttonComp from '@/components/misc/buttonComp.vue'
export default {
  name: 'Packages',
  components: {
    buttonComp,
  },
  data() {
    return {
      Packages: [
        {
          id: 0,
          img: 'appdev.png',
          package: 'App development',
          desc:
            'App devLorem, ipsum dolor sit amet consectetur adipisicing elit. Consequatuporro, architecto totam recusandae praesentium.',

          slashedPrice: 240,
          price: 149,
        },
        {
          id: 1,
          img: 'desktop.png',
          package: 'Web development',
          desc:
            'App devLorem, ipsum dolor sit amet consectetur adipisicing elit. Consequatuporro, architecto totam recusandae praesentium.',

          slashedPrice: 149,
          price: 299,
        },
        {
          id: 2,
          img: 'appdev.png',
          package: 'Full development',
          desc:
            'App devLorem, ipsum dolor sit amet consectetur adipisicing elit. Consequatuporro, architecto totam recusandae praesentium.',

          slashedPrice: 120,
          price: 999,
        },
        {
          id: 3,
          img: 'Edit4.png',
          package: 'Personalised',
          desc:
            'App devLorem, ipsum dolor sit amet consectetur adipisicing elit. Consequatuporro, architecto totam recusandae praesentium.',

          slashedPrice: 399,
          price: '1000+',
        },
      ],
    }
  },
}
</script>

<style scoped>
@media (min-width: 1024px) {
  .package {
    min-width: 0;
  }
}
</style>
