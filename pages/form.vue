<template>
  <div class="container">
    <section class="container__routing">
      <nuxt-link class="route" to="/">Back Home</nuxt-link>
      <Form />
    </section>
  </div>
</template>

<style>
.container {
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
}
section {
  display: flex;
  flex-direction: column;
}
.container__routing nuxt-link {
  margin-bottom: 20px;
}
</style>
