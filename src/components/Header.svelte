<script>
  export let y;

  let isMenuOpen = false;

  let tabs = [
    { name: "Projects", link: "#projects" },
    { name: "About Me", link: "#about" },
    { name: "Experience", link: "#experience" },
    // { name: "Blog", link: "#" }, // Optional
  ];

  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }
</script>

<header
  class={"sticky z-[10] top-0 duration-200 px-6 py-4 flex items-center justify-between border border-solid" +
    (y > 0
      ? "py-4 bg-slate-950 border-violet-950"
      : "py-6 bg-transparent border-transparent")}
>
  <h1 class="font-medium text-xl">
    <b class="font-bold poppins">Pande</b> Praditya
  </h1>
  <div class="sm:flex ml-auto pr-4 items-center gap-4 hidden">
    {#each tabs as tab, index}
      <a href={tab.link} class="duration-200 hover:text-violet-400">
        <p>{tab.name}</p>
      </a>
    {/each}
  </div>

  <a
    href="mailto:pandepraditya@gmail.com"
    target="_blank"
    class="blueShadow relative overflow-hidden px-5 py-2 group rounded-full bg-white text-slate-950 hidden sm:inline-block"
  >
    <div
      class="absolute top-0 right-full w-full h-full bg-violet-400 opacity-20 group-hover:translate-x-full z-0 duration-200"
    ></div>
    <h4 class="relative z-[9]">Get in touch</h4>
  </a>

  <!-- Mobile Toggle -->
  <button class="text-2xl sm:hidden ml-auto" on:click={toggleMenu}>
    {#if isMenuOpen}
      <i class="fa-solid fa-xmark"></i>
    {:else}
      <i class="fa-solid fa-bars"></i>
    {/if}
  </button>

  <!-- Mobile Menu -->
  {#if isMenuOpen}
    <div
      class="sm:hidden absolute top-16 left-0 w-full bg-slate-900 border-t border-slate-700 flex flex-col gap-6 p-6 text-lg z-[9]"
    >
      {#each tabs as tab}
        <a
          href={tab.link}
          class="hover:text-violet-400"
          on:click={() => (isMenuOpen = false)}
        >
          {tab.name}
        </a>
      {/each}

      <a
        href="mailto:yourname@gmail.com"
        class="mt-2 blueShadow relative overflow-hidden px-5 py-2 group rounded-full bg-white text-slate-950 w-fit"
      >
        <div
          class="absolute top-0 right-full w-full h-full bg-violet-400 opacity-20 group-hover:translate-x-full z-0 duration-200"
        ></div>
        <h4 class="relative z-[9]">Get in touch</h4>
      </a>
    </div>
  {/if}
</header>
