<template>
  <div class="w-9/10">
    <h3 class="text-2xl font-semibold text-left mb-5">Our Packages</h3>
    <div class="w-full overflow-x-auto">
      <div class="w-full flex rounded-lg">
        <div
          v-for="(item, id) in Packages"
          :key="id"
          class="px-6 py-4 mx-4 lg:min-w-0 lg:m-0 border-r-2 bg-app-gray-2 min-w-full text-sm border-app-gray-1 shadow-2xl h-auto"
        >
          <img :src="item.img" alt="pack" />
          <img src="/static/packages/leaf.png" alt="" />
          <h4 class="text-xl mb-4 font-medium">{{ item.package }}</h4>
          <p>{{ item.desc }}</p>
          <p class="mt-4">{{ item.works }}</p>
          <p class="mt-4">
            <span class="mr-2 text-sm line-through"
              >${{ item.slashedPrice }}</span
            >
            <span class="text-app-green-1 text-xl line-through font-medium"
              >${{ item.price }}</span
            >
          </p>
          <ButtonComp />
          <p>Edit request? <span class="font-medium">ContactUs</span></p>
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
          img: '/static/packages/personalized.png',
          package: 'App development',
          desc:
            'with additional offline features enabled by desktop applications for macOS and Windows',
          works: 'hear fromme when we meet on  on tge batteke grouhnd',
          slashedPrice: 240,
          price: 210,
        },
        {
          id: 1,
          img: '/static/packages/personalized.png',
          package: 'Web development',
          desc:
            'with additional offline features enabled by desktop applications for macOS and Windows',
          works: 'hear fromme when we meet on  on tge batteke grouhnd',
          slashedPrice: 149,
          price: 120,
        },
        {
          id: 2,
          img: '/static/packages/personalized.png',
          package: 'full development',
          desc:
            'with additional offline features enabled by desktop applications for macOS and Windows',
          works: 'hear fromme when we meet on  on tge batteke grouhnd',
          slashedPrice: 120,
          price: 128,
        },
        {
          id: 3,
          img: '/static/packages/personalized.png',
          package: 'personalised',
          desc:
            'with additional offline features enabled by desktop applications for macOS and Windows',
          works: 'hear fromme when we meet on  on tge batteke grouhnd',
          slashedPrice: 399,
          price: 129,
        },
      ],
    }
  },
}
</script>

<style scoped></style>
