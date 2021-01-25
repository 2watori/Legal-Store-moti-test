<template>
  <main class="main font-body" >
    <div>
        {{ title }}
    </div>
    <div>
        {{ category.name }}
    </div>
    <img :src="`${ image.url }?fit=crop&w=1000&h=1000`" alt="">
    <div class="text-gray-800 text-xl">
        {{ price }} yen / {{ unit.value }}{{ unit.unit }}
    </div>
    <div>
        {{ date }}
    </div>
  </main>
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