<template>
  <div class="container">
    <div v-for="item in data" :key="item.id">
      <div>{{ item.username }} {{ item.password }}</div>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params, $strapi }) {
    const data = await $strapi.$tests.find()
    return { data }
  },
}
</script>
