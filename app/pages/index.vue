<template>
  <section class="home">
    <div class="py-24 md:py-36 mx-auto flex flex-wrap flex-col md:flex-row items-center">
      <div class="flex flex-col w-full xl:w-3/5 justify-center lg:items-start overflow-y-hidden">
        <div v-html="$md.render(welcomeText)" class="home__welcome markdown" />
        <div>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Illo expedita quaerat, neque
          similique incidunt odio non eaque nulla recusandae velit labore maxime! Laborum,
          perspiciatis adipisci! Tempora molestiae voluptatem eius ratione.
        </div>
        <div class="mt-4">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Illo expedita quaerat, neque
          similique incidunt odio non eaque nulla recusandae velit labore maxime! Laborum,
          perspiciatis adipisci! Tempora molestiae voluptatem eius ratione.
        </div>
        <div class="mt-4">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Illo expedita quaerat, neque
          similique incidunt odio non eaque nulla recusandae velit labore maxime! Laborum,
          perspiciatis adipisci! Tempora molestiae voluptatem eius ratione.
        </div>
        <div class="mt-4">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Illo expedita quaerat, neque
          similique incidunt odio non eaque nulla recusandae velit labore maxime! Laborum,
          perspiciatis adipisci! Tempora molestiae voluptatem eius ratione.
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';
import settings from '@/content/settings/general.json';

@Component({
  // Called to know which transition to apply
  transition() {
    return 'slide-left';
  },
})
export default class Home extends Vue {
  welcomeText = settings.welcomeText;

  get posts(): Post[] {
    return this.$store.state.posts;
  }

  isSignedUp = false;

  form = {
    email: '',
  };

  encode(data): string {
    return Object.keys(data)
      .map((key) => `${encodeURIComponent(key)}=${encodeURIComponent(data[key])}`)
      .join('&');
  }

  validEmail(email): boolean {
    // eslint-disable-next-line
    const re = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
    return re.test(email);
  }

  async handleSubmit(): Promise<void> {
    if (!this.validEmail(this.form.email)) {
      this.$refs.emailInput.focus();
      return;
    }

    try {
      await fetch('/', {
        method: 'POST',
        headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
        body: this.encode({ 'form-name': 'signups', ...this.form }),
      });

      this.isSignedUp = true;
    } catch (error) {
      console.error(error);
    }
  }
}
</script>
