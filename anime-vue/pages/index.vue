<template>
  <section class="flex flex-col justify-center items-center">
    <Card />
  </section>
</template>

<script lang="ts">
import Vue from 'vue'
import Card from '~/components/card.vue'

export default Vue.extend({
    name: "IndexPage",
    components: { Card }
})
</script>
