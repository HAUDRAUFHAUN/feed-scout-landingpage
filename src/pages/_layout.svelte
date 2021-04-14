<script>
  import Footer from "$components/layout/Footer.svelte";
  import Nav from "$components/layout/Nav.svelte";
</script>

<div
  class="flex flex-col min-h-screen w-screen text-gray-900 bg-white dark:bg-gray-800 dark:text-white"
>
  <Nav />
  <div class="grid place-content-center text-gray-900 bg-white dark:text-gray-900 dark:text-white w-screen h-full">
    <slot />
  </div>
  <Footer />
</div>
