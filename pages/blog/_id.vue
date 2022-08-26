<template>
  <article>
   
    <h1>{{ page.title }}</h1>
    <nuxt-content :document="page" />
    <!--
    {{page}}
    -->
  </article>
</template>
<script>
export default {
  async asyncData ({ $content, params }) {
    // console.log(`blog/${params.id}`)
    const page = await $content(`blog/${params.id}`).fetch()
    // console.log({page})
    // const page = await $content(`blog`, `hello`).fetch()
    return {
      page
    }
  }
}
</script>