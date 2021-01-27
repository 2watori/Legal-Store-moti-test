<template>
    <div class="main max-w-7xl m-auto font-body">
        <!-- header -->
        <div class="flex items-center px-4 py-6 sm:px-6 lg:px-8 lg:py-8">
            <svg
                class="w-8 mr-2 text-purple-600"
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
            >
                <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M5 13l4 4L19 7"
                />
            </svg>
            <div class="text-purple-600 text-2xl font-bold">
                <nuxt-link to="./">
                    Legal Store
                </nuxt-link> 
            </div>
      
            <div class="hidden sm:block ml-auto">
                <div div class="flex items-baseline space-x-4">
                    <div class="text-purple-600 hover:bg-gray-100 px-4 py-2 rounded-md text-base font-semibold">
                        <nuxt-link to="/store">
                            Store
                        </nuxt-link>
                    </div>
                    <div class="text-purple-600 hover:bg-gray-100 px-4 py-2 rounded-md text-base font-semibold">
                        <nuxt-link to="/contact">
                            Contact
                        </nuxt-link>
                    </div>
                </div>
            </div>
        </div>

        <!-- main -->
        <main class="my-4 px-4 sm:my-6 sm:px-8 xl:my-8">
            <div class="pb-4 sm:pb-8 text-lg">
                <span class="text-purple-600 hover:text-purple-400">
                    <nuxt-link to="/">
                        Home
                    </nuxt-link>
                </span>
                <span class="px-2">
                    /
                </span>
                <span class="text-purple-600 hover:text-purple-400">
                    <nuxt-link to="/store">
                        Store
                    </nuxt-link>
                </span>
                <span class="px-2">
                    /
                </span>
                {{ entitle }}
            </div>
            <div class="lg:flex">
                <div class="w-full lg:w-2/3">
                    <img class="rounded-xl" :src="`${ image.url }?fit=crop&w=1000&h=750`" alt="">
                </div>

                <div class="lg:w-1/3 py-8 lg:py-0 lg:pl-8">
                    <div>
                        <div class="text-4xl font-extrabold text-gray-900 sm:text-5xl md:text-6xl">
                            {{ title }}
                        </div>
                        <div class="mt-2 text-xl font-semibold text-gray-900">
                            {{ entitle }}
                        </div>
                    </div>
                    
                    <div class="my-4">
                        <div class="inline px-3 py-1 leading-7 text-white text-base rounded" :style="`background-color: ${ category.color };`">
                            {{ category.name }}
                        </div>
                    </div>

                    <div>
                        <div class="text-gray-700">
                            by
                            <span :style="`color: ${ category.color };`">
                                <a href="https://twitter.com/_moti3756">
                                    moti3756
                                </a>
                            </span>
                        </div>
                    </div>

                    <div>
                        <div class="pt-4 text-gray-700 font-bold text-xl">
                            {{ description }}
                        </div>
                    </div>

                    <div class="my-4 bg-gray-100 rounded">
                        <div class="px-6 py-4 text-gray-700 font-bold text-2xl">
                            {{ price }} yen / {{ unit.value }}{{ unit.unit }}
                        </div>
                    </div>
                

                    <div class="text-gray-500 text-base">
                        配送日：{{ date }}
                    </div>

                    <div class="flex items-center justify-center mt-4 sm:mt-8 px-8 py-3 md:py-4 md:px-10 text-white bg-purple-600 hover:bg-purple-700 rounded-md">
                        <nuxt-link to="/store">
                            {{ price }} yen - Add to Cart
                        </nuxt-link>
                    </div>
                </div>
            </div>
        </main>
    </div> 
</template>

<script>
import axios from 'axios'

export default {
  async asyncData({ params }) {
    const { data } = await axios.get(
      `https://moti3756.microcms.io/api/v1/store/${params.slug}`,
      {
        headers: { 'X-API-KEY': '610de392-6c1c-4219-81a6-3ac1bee282d6' }
      }
    )
    return data
  }
}
</script>