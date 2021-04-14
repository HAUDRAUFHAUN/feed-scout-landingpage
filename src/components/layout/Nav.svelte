<script>
  import { darkTheme } from "$stores/stores.js";

  let hideMenu = true;

  let menuItems = [
    { name: "Home", route: "/", target: "" },
    { name: "About", route: "/about", target: "" },
    {
      name: "GitHub",
      route: "https://github.com/HAUDRAUFHAUN/feed-scout",
      target: "_blank",
    },
  ];

  function setTheme() {
    try {
      darkTheme.update((n) => !n);
      if ($darkTheme) {
        document.documentElement.classList.add("dark");
      } else {
        document.documentElement.classList.remove("dark");
      }
    } catch (error) {
      console.log(error);
    }
  }
</script>

<section class="bg-transparent dark:bg-gray-800 dark:text-white">
  <nav
    class="hidden md:flex md:flex-row md:justify-between px-2 pt-3 pb-4 lg:px-4 lg:pt-6 lg:pb-8 xl:px-6 xl:pt-8 xl:pb-10"
  >
    <header>
      <a href="/">📰</a>
    </header>
    <main class="flex flex-row space-x-3">
      {#each menuItems as item}
        <a
          href={item.route}
          rel="prefetch"
          target={item.target}
          class="font-medium text-teal-500 dark:text-teal-50 dark:hover:text-teal-600 py-3 px-4 rounded-md hover:bg-teal-50 dark:hover:bg-teal-100"
          >{item.name}</a
        >
      {/each}
    </main>

    <button
      on:click={() => setTheme()}
      class="focus:outline-none hover:bg-gray-100 dark:hover:bg-gray-700 p-2 rounded-md flex justify-center items-center"
      ><svg
        xmlns="http://www.w3.org/2000/svg"
        class="h-6 w-6"
        fill="none"
        viewBox="0 0 24 24"
        stroke="currentColor"
      >
        {#if $darkTheme}
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z"
          />
        {:else}
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364 6.364l-.707-.707M6.343 6.343l-.707-.707m12.728 0l-.707.707M6.343 17.657l-.707.707M16 12a4 4 0 11-8 0 4 4 0 018 0z"
          />
        {/if}
      </svg></button
    >
  </nav>

  <nav class="flex justify-between md:hidden px-2 pt-3 pb-4">
    <button
      class="focus:outline-none hover:bg-gray-100 dark:hover:bg-gray-700 p-2 rounded-md flex justify-center items-center"
    >
      <svg
        xmlns="http://www.w3.org/2000/svg"
        class="h-6 w-6"
        fill="none"
        viewBox="0 0 24 24"
        stroke="currentColor"
        ><path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M4 6h16M4 12h16M4 18h16"
        /></svg
      >
    </button>
    <header>
      <a href="/">📰</a>
    </header>

    <button
      on:click={() => setTheme()}
      class="focus:outline-none hover:bg-gray-100 dark:hover:bg-gray-700 p-2 rounded-md flex justify-center items-center"
      ><svg
        xmlns="http://www.w3.org/2000/svg"
        class="h-6 w-6"
        fill="none"
        viewBox="0 0 24 24"
        stroke="currentColor"
        ><path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364 6.364l-.707-.707M6.343 6.343l-.707-.707m12.728 0l-.707.707M6.343 17.657l-.707.707M16 12a4 4 0 11-8 0 4 4 0 018 0z"
        /></svg
      ></button
    >
  </nav>
</section>
