<template>
  <footer class="footer -mx-4 md:mx-0">
    <nav class="nav ml-auto">
      <ul class="flex flex-row items-center sm:mt-4 sm:pt-4 md:mt-0 md:pt-0 md:mr-4 lg:mr-8">
        <li>
        <a href="/files/002 2022.11.10 Complaint.pdf">The Complaint</a>
        </li>
        <li>
          <nuxt-link to="/press" class="block font-medium px-4 py-1 md:p-2 lg:px-4">
            Press
          </nuxt-link>
        </li>
        <li
          v-for="(page, index) in pages"
          :key="index"
          class="block font-medium px-4 py-1 md:p-2 lg:px-4"
        >
          <nuxt-link :to="`/${page.slug}`">{{ page.title }}</nuxt-link>
        </li>
      </ul>
    </nav>
  </footer>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';

@Component
export default class Footer extends Vue {}
</script>

<style lang="scss">
.footer {
  background-color: $bluise;
}
</style>
