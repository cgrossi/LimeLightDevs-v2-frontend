<template>
  <div class="container mx-auto px-5 2xl:px-0 atest">
    <nav class="flex justify-between py-4 items-center">
      <div>
        <nuxt-link to="/">
          <div>
            <div class="text-custom-green-100 inline text-4xl">
              <span class="font-bold">Lime</span><span>light</span>
            </div>
            <span class="text-green-700">devs</span>
          </div>
        </nuxt-link>
      </div>
      <ul class="flex space-x-24">
        <li v-for="link in links" :key="link.name">
          <nuxt-link to="/">
            <span
              v-if="!link.button"
              class="hover:text-custom-green-100 duration-200 ease-in-out"
            >
              {{ link.name }}
            </span>
            <button
              v-else
              class="px-4 py-1 bg-custom-green-100 text-black rounded-full hover:bg-opacity-75 duration-200"
            >
              {{ link.name }}
            </button>
          </nuxt-link>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  setup() {
    const links = [
      {
        name: 'Services',
        to: '#services',
      },
      {
        name: 'Packages',
        to: '#packages',
      },
      {
        name: 'Works',
        to: '#works',
      },
      {
        name: 'Contact Us',
        to: '#contact',
        button: true,
      },
    ]
    return {
      links,
    }
  },
}
</script>

<style></style>
