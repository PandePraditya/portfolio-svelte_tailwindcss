<script>
  import { createEventDispatcher } from "svelte";

  export let work;

  const dispatch = createEventDispatcher();
</script>

<div
  class="p-4 sm:p-6 flex flex-col gap-4 rounded-lg border border-solid border-blue-700 text-center group hover:border-blue-500 duration-200"
>
  <div
    class="bg-slate-950 grid place-items-center px-4 text-5xl md:text-6xl -mt-10 sm:-mt-12 md:-mt-14 lg:-mt-16 mx-auto duration-200"
  >
    <i class={work.icon} aria-hidden="true"></i>
  </div>
  <div
    class="flex items-center justify-center w-auto mx-auto border rounded-full px-5 hover:bg-slate-900 duration-200"
  >
    <span class="font-light text-base lg:text-lg md:text-xl"
      >{work.tech || "-"}</span
    >
  </div>
  <h3 class="font-medium text-xl sm:text-2xl md:text-3xl">
    {work.name}
  </h3>
  {#if work.client || work.period}
    <h4 class="text-blue-500 text-lg font-medium">
      {work.client}
    </h4>
    {#if work.client && work.period}
      <p class="text-slate-400">{work.period}</p>
    {:else}
      <p class="text-slate-400">Period not specified</p>
    {/if}
  {/if}
  <p>{work.description}</p>
  <div class="flex-1 flex justify-between gap-4 items-center">
    <button
      class="ml-auto px-2 rounded-md cursor-pointer hover:text-slate-950 duration-200 relative after:absolute after:top-0 after:right-full after:w-full after:h-full after:bg-white after:duration-200 hover:after:translate-x-full after:z-[-1] overflow-hidden focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-blue-500"
      on:click={() => dispatch("preview", work)}
    >
      <p class="relative z-4">
        Preview <span class="sr-only">{work.name}</span>→
      </p>
    </button>
  </div>
</div>
