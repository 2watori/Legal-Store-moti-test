<template>
    <div class="max-w-7xl m-auto font-body">
        <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 sm:gap-8 my-8 px-4 sm:my-12 sm:px-8 lg:my-12 xl:my-16">
            <div v-for="content in contents" :key="content.id" class="bg-gray-100 pb-6 rounded-lg">
                <nuxt-link :to="`/${content.id}`">
                    <div>
                        <img class="w-full rounded-t-lg" :src="`${ content.image.url }?fit=crop&w=500&h=250`" alt="">
                    </div>
                </nuxt-link>

                <div class="mt-4 px-6">
                    <nuxt-link :to="`/${content.id}`">
                        <div class="inline text-gray-800 hover:text-purple-600 text-3xl font-bold">
                            {{ content.title }}
                        </div>
                    </nuxt-link>

                    <div class="flex mt-4">
                        <div class="px-4 py-1 leading-7 bg-gray-300 text-gray-800 text-lg font-bold rounded">
                            {{ content.price }} yen / {{ content.unit.value }}{{ content.unit.unit }}
                        </div>
                        
                        <div class="mx-6 px-3 py-1 leading-7 text-white text-base rounded" :style="`background-color: ${ content.category.color };`">
                            {{ content.category.name }}
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from "axios";

export default {
  async asyncData() {
    const { data } = await axios.get(
      // your-service-id部分は自分のサービスidに置き換えてください
      "https://moti3756.microcms.io/api/v1/store",
      {
        // your-api-key部分は自分のapi-keyに置き換えてください
        headers: { "X-API-KEY": "610de392-6c1c-4219-81a6-3ac1bee282d6" },
      }
    );
    return data;
  },
};
</script>

