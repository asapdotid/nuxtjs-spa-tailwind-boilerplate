<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">
        <fa :icon="['fas', 'home']" /> Nuxt SPA + Tailwind CSS Boilerplate
      </h1>
      <div class="links">
        <div>
          <h3>Mountaiins (Sample from NuxtJs Dev API)</h3>
          <ul v-for="mountain in mountains" :key="mountain.slug">
            <li>{{ mountain.title }}</li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $axios, $config }) {
    const mountains = await $axios.$get(`/mountains`)
    return { mountains }
  },
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.container {
  @apply bg-green-100 mt-3;
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 60px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
