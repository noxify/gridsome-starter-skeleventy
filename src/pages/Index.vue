<template>
  <Layout>
    <section id="container-centre" class="column centre flex-1">
      <h1 class="page-title">Welcome to Skeleventy!</h1>
      <div class="content">
        <p>
          A 
          <a href="https://www.gridsome.org">gridsome</a> starter built with
          <a href="https://tailwindcss.com">TailwindCSS</a>.
        </p>
        <h2 class="text-3xl">Features</h2>
        <ul class="mb-12 list-disc pl-4">
          <li>Build sites faster with the power of Gridsome, TailwindCSS and SCSS</li>
          <li>Image lazyloading</li>
          <li>A simple blog with categories and featured images</li>
        </ul>
        <h2 class="text-3xl">Credits</h2>
        <p>
          This template was built for <a href="https://www.11ty.dev/docs/" target="_blank">Eleventy</a> by <a href="https://github.com/josephdyer" target="_blank"> Joseph Dyer</a>.
        </p>
      </div>
    </section>
  </Layout>
</template>

<script>
export default {
  metaInfo: {
    title: "Home"
  }
};
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
