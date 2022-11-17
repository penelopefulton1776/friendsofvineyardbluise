/* eslint-disable */
<template>
  <section class="edit">
    <div class="py-24 md:py-36 mx-auto max-w-sm">
      <h4 class="text-2xl text-center">Edit blog</h4>
      <div class="mb-2">
        <label for="Title">
          <p>Title</p>
          <input
            type="text"
            class="form-control block w-full px-4 py-2 text-xl font-normal text-gray-700 bg-white bg-clip-padding border border-solid border-gray-500 rounded transition ease-in-out m-0 focus:text-gray-700 focus:bg-white focus:border-blue-700 focus:outline-none"
            placeholder="Title"
          />
        </label>
      </div>
      <div class="mb-2">
        <label for="Description">
          <p>Description</p>
          <textarea
            type="text"
            class="form-control block w-full px-4 py-2 text-xl font-normal text-gray-700 bg-white bg-clip-padding border border-solid border-gray-500 rounded transition ease-in-out m-0 focus:text-gray-700 focus:bg-white focus:border-blue-700 focus:outline-none"
            placeholder="Description"
          />
        </label>
      </div>
      <div class="mb-2">
        <label for="formFile" class="form-label inline-block mb-2 text-gray-700">
          <p>Upload file</p>
          <input
            class="form-control block w-full px-3 py-1.5 text-base font-normal text-gray-700 bg-white bg-clip-padding border border-solid border-gray-400 rounded transition ease-in-out m-0 focus:text-gray-700 focus:bg-white focus:border-blue-600 focus:outline-none"
            type="file"
            id="formFile"
          />
        </label>
      </div>
      <div class="mb-2">
        <div>
          <button
            class="inline-block px-7 py-3 bg-blue-600 text-white font-medium text-sm leading-snug uppercase rounded shadow-md hover:bg-blue-700 hover:shadow-lg focus:bg-blue-700 focus:shadow-lg focus:outline-none focus:ring-0 active:bg-blue-800 active:shadow-lg transition duration-150 ease-in-out px-4 w-full"
            data-mdb-ripple="true"
            data-mdb-ripple-color="light"
          >
            submit
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';

@Component({
  // Called to know which transition to apply
  transition() {
    return 'slide-left';
  },
})
export default class Home extends Vue {}
</script>
