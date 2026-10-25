<script>
  // Dynamic year for copyright
  let currentYear = new Date().getFullYear();
</script>

<footer class="relative pt-24 pb-16 border-t border-violet-900/40 z-[0]">
  <!-- Top Line Accent -->
  <div class="absolute top-0 left-1/2 -translate-x-1/2 w-40 h-1 
              bg-blue-700 rounded-full">
  </div>

  <div class="max-w-3xl mx-auto px-6 flex flex-col items-center gap-12">

    <!-- Contact Card -->
    <div class="px-10 py-8 flex flex-col items-center gap-4 shadow-xl">

      <p class="text-xl font-semibold text-white tracking-wide">
        Connect with me
      </p>

      <p class="text-sm text-slate-400">
        Feel free to reach out or explore my work
      </p>

      <div class="flex flex-col gap-3 text-slate-300 text-sm">

        <div class="flex items-center gap-3">
          <i class="fa-brands fa-whatsapp text-blue-500 text-2xl" aria-hidden="true"></i>
          <a href="https://wa.me/628113866745" target="_blank" rel="noopener noreferrer"
             class="hover:text-cyan-500 transition">wa.me/628113866745<span class="sr-only"> (opens in a new tab)</span></a>
        </div>

        <div class="flex items-center gap-3">
          <i class="fa-solid fa-envelope text-blue-500 text-2xl" aria-hidden="true"></i>
          <a href="mailto:pandepraditya@gmail.com"
             class="hover:text-cyan-500 transition">pandepraditya@gmail.com</a>
        </div>

        <div class="flex items-center gap-3">
          <i class="fa-brands fa-github text-blue-500 text-2xl" aria-hidden="true"></i>
          <a href="https://github.com/PandePraditya" target="_blank" rel="noopener noreferrer"
             class="hover:text-cyan-500 transition">github.com/PandePraditya<span class="sr-only"> (opens in a new tab)</span></a>
        </div>

        <div class="flex items-center gap-3">
          <i class="fa-brands fa-linkedin text-blue-500 text-2xl" aria-hidden="true"></i>
          <a href="https://linkedin.com/in/pande-praditya/" target="_blank" rel="noopener noreferrer"
             class="hover:text-cyan-500 transition">linkedin.com/in/pande-praditya<span class="sr-only"> (opens in a new tab)</span></a>
        </div>

      </div>
    </div>

    <!-- Bottom Note -->
    <p class="text-xs text-slate-400">
      &copy; {currentYear} Pande Praditya
    </p>

  </div>
</footer>
