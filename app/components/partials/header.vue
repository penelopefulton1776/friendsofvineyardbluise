<template>
  <header class="flex items-center py-4 md:py-8">
    <nav class="nav ml-auto">
      <ul class="flex flex-row items-center sm:mt-4 sm:pt-4 md:mt-0 md:pt-0 md:mr-4 lg:mr-8">    
        <li>
        <nuxt-link to="/" class="block font-medium px-4 py-1 md:p-2 lg:px-4">
          Home
          </nuxt-link>
        </li> 
		    <li>
          &nbsp;&nbsp;&nbsp;&nbsp;
        </li> 
        <li>
	       <a href="/files/DPA warning to SoCal AAPI Community.pdf">DPA warning to SoCal AAPI Community</a>
        </li>
        <li>
          &nbsp;&nbsp;&nbsp;&nbsp;
        </li>
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
  </header>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';
import settings from '@/content/settings/general.json';

@Component
export default class Header extends Vue {
  get pages(): Page[] {
    return this.$store.state.pages;
  }

  logo = settings.logo;
}
</script>

<style lang="scss">
.nav {
  ul li > a {
    &.nuxt-link-active {
      color: $bluise;
      @apply font-bold;
    }
  }
}
</style>
