<template>
  <div class="max-w-7xl m-auto font-body">
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
      <div class="text-purple-600 text-2xl font-bold">Legal Store</div>
      
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
    <main
      class="mt-10 mx-auto px-4 sm:mt-12 sm:px-6 md:mt-16 lg:mt-20 lg:px-8 xl:mt-28"
    >
      <div class="sm:text-center lg:text-left">
        <h1
          class="text-4xl tracking-tight font-extrabold text-gray-900 sm:text-5xl md:text-6xl"
        >
          <span class="block xl:inline">You can get</span>
          <span class="block text-purple-600 xl:inline">legitimate items.</span>
        </h1>
        <p
          class="mt-3 text-base text-gray-500 sm:mt-5 sm:text-lg sm:max-w-xl sm:mx-auto md:mt-5 md:text-xl lg:mx-0"
        >
          We buy things that look illegal but are actually all legally available at a reasonable price. Also, this store is fictitious.
        </p>
      </div>
      <div class="mt-5 sm:mt-8 sm:flex sm:justify-center lg:justify-start">
        <div class="rounded-md">
          <nuxt-link to="/store" class="w-full flex items-center justify-center px-8 py-3 border border-transparent text-base font-medium rounded-md text-white bg-purple-600 hover:bg-purple-700 md:py-4 md:text-lg md:px-10">
            Go to store
          </nuxt-link>
        </div>
      </div>
    </main>

    <div class="mt-10 mx-auto px-4 sm:mt-12 sm:px-8 md:mt-16 lg:mt-20 lg:px-8 xl:mt-28">
      <div class="text-4xl tracking-tight font-extrabold text-gray-900 sm:text-5xl md:text-6xl">
      Latest
      </div>
      <p
        class="mt-3 text-base text-gray-500 sm:mt-5 sm:text-lg sm:max-w-xl sm:mx-auto md:mt-5 md:text-xl lg:mx-0"
      >
        Click on the image or title to go to the detail page.
      </p>
    </div>

    <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 sm:gap-6 md:gap-8 my-8 px-4 sm:my-12 sm:px-8 lg:my-12 xl:my-16">
      <div v-for="content in contents" :key="content.id" class="bg-gray-100 pb-4 md:pb-6 rounded-lg">
        <nuxt-link :to="`/${content.id}`">
          <div>
            <img class="w-full rounded-t-lg" :src="`${ content.image.url }?fit=crop&w=500&h=250`" alt="">
          </div>
        </nuxt-link>

        <div class="mt-3 px-4 md:pt-2 md:px-6">
          <nuxt-link :to="`/${content.id}`">
            <div class="inline text-gray-800 hover:text-purple-600 text-3xl font-bold">
              {{ content.title }}
            </div>
          </nuxt-link>

          <div class="flex mt-3 md:mt-4">
            <div class="px-4 py-1 leading-7 bg-gray-300 text-gray-800 text-lg font-bold rounded">
              {{ content.price }} yen / {{ content.unit.value }}{{ content.unit.unit }}
            </div>
            <div class="ml-4 md:ml-6 px-2 py-1 leading-7 text-white text-base font-medium rounded" :style="`background-color: ${ content.category.color };`">
              {{ content.category.name }}
            </div>
          </div>
        </div>
      </div>
    </div>

    <div
      class="mt-10 mx-auto px-4 sm:mt-12 sm:px-6 md:mt-16 lg:mt-20 lg:px-8 xl:mt-28"
    >
      <div class="sm:text-center lg:text-left">
        <h1
          class="text-4xl tracking-tight font-extrabold text-gray-900 sm:text-5xl md:text-6xl"
        >
          <span class="block xl:inline">About</span>
          <span class="block text-purple-600 xl:inline">Legal Store</span>
        </h1>
        <p
          class="mt-3 text-base text-gray-500 sm:mt-5 sm:text-lg sm:max-w-xl sm:mx-auto md:mt-5 md:text-xl lg:mx-0"
        >
          This is a website I created on a whim. All of them are fictitious, so they are not actually for sale.
        </p>
      </div>
    </div>

    <div class="px-4 sm:px-6 lg:px-8">

    <div class="mt-12">
      <dl class="space-y-10 md:space-y-0 md:grid md:grid-cols-2 md:gap-x-8 md:gap-y-10">
        <div class="flex">
          <div class="flex-shrink-0">
            <div class="flex items-center justify-center h-12 w-12 rounded-md bg-purple-600 text-white">
              <!-- Heroicon name: globe-alt -->
              <svg class="w-6 h-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
              </svg>
            </div>
          </div>
          <div class="ml-4">
            <dt class="text-lg leading-6 font-medium text-gray-900">
              Everything is legal.
            </dt>
            <dd class="mt-2 text-base text-gray-500">
              All of them are not illegal. If anything, they are not even for sale.
            </dd>
          </div>
        </div>

        <div class="flex">
          <div class="flex-shrink-0">
            <div class="flex items-center justify-center h-12 w-12 rounded-md bg-purple-600 text-white">
              <!-- Heroicon name: scale -->
              <svg class="w-6 h-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 8l3 5m0 0l3-5m-3 5v4m-3-5h6m-6 3h6m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />
              </svg>
            </div>
          </div>
          <div class="ml-4">
            <dt class="text-lg leading-6 font-medium text-gray-900">
              Everything can be purchased in Japanese yen.
            </dt>
            <dd class="mt-2 text-base text-gray-500">
              In fact, it won't cost you any money and you won't receive any goods because you don't sell them in the first place. I mean, what is the purpose of this site?
            </dd>
          </div>
        </div>
      </dl>
    </div>
  </div>

  <footer class="px-4 sm:px-8 mt-10 sm:mt-12 md:mt-16 lg:mt-20 xl:mt-28 mb-10">
    <div class="sm:flex items-center bg-gray-100 rounded-xl px-4 py-6 sm:px-6 lg:px-8 lg:py-8">
      <div class="text-gray-900 text-base font-semibold text-center">©2021 moti3756</div>
      <div class="hidden sm:block ml-auto">
        <div class="flex">

        <svg class="w-6 h-6 text-purple-600" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13.828 10.172a4 4 0 00-5.656 0l-4 4a4 4 0 105.656 5.656l1.102-1.101m-.758-4.899a4 4 0 005.656 0l4-4a4 4 0 00-5.656-5.656l-1.1 1.1" />
        </svg>

        <a class="ml-4 text-purple-600 hover:text-purple-400 text-base font-semibold" href="https://twitter.com/_moti3756" target="_blunk">
          Twitter
        </a>

        <a class="ml-4 text-purple-600 hover:text-purple-400 text-base font-semibold" href="https://moti3756.netlify.app/" target="_blunk">
          Website
        </a>
        </div>
      </div>
    </div>
  </footer>

  </div>
</template>

<script>
import axios from "axios";

export default {
  async asyncData() {
    const limit = 4
    const { data } = await axios.get(
      // your-service-id部分は自分のサービスidに置き換えてください
      `https://moti3756.microcms.io/api/v1/store?limit=${limit}`,
      {
        // your-api-key部分は自分のapi-keyに置き換えてください
        headers: { "X-API-KEY": "610de392-6c1c-4219-81a6-3ac1bee282d6" },
      }
    );
    return data;
  },
};
</script>