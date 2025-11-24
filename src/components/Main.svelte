<script>
  import Work from "./Work.svelte";
  import Typewriter from "./Typewriter.svelte";

  const words = [
    "Full-Stack Developer",
    "Web Quality Assurance",
    "Laravel Enthusiast",
    "Problem Solver"
  ];

  let works = [
    {
      name: "Timedoor Inventory",
      tech: "Laravel + Nuxt.js",
      icon: "fa-solid fa-boxes-stacked",
      description:
        "Timedoor Inventory is an inventory management system with an integrated CMS for PT. Timedoor Indonesia. It is built in laravel with a register by admin approval that sends the user credentials through email. The frontend is built with Nuxt.js and TailwindCSS, hosted on AWS EC2. It features CRUD operations for managing inventory data efficiently, along with QR Code generation for easy access to specific items.",
      images: [
        "/images/works/work-1/landing-page.webp",
        "/images/works/work-1/login.webp",
        "/images/works/work-1/inquiries.webp",
        "/images/works/work-1/dashboard.webp",
      ],
    },
    {
      name: "Makardhi Jobfair",
      tech: "Laravel + TailwindCSS",
      icon: "fa-solid fa-briefcase",
      description:
        "Makardhi Jobfair is a job fair website for Bali Tourism Polytechnic, built with Laravel and TailwindCSS. It includes job listings, company profiles, and an application system for students and the public.",
      images: [
        "/images/works/work-2/welcome.webp",
        "/images/works/work-2/landing-page.webp",
        "/images/works/work-2/login-admin.webp",
        "/images/works/work-2/admin-page.webp",
      ],
    },
    {
      name: "Paskamras Recruitment",
      tech: "Laravel + Vue.js",
      icon: "fa-solid fa-handshake",
      description:
        "Paskamras Recruitment is a recruitment website for ITB STIKOM Bali’s Paskamras club. Built with Laravel and Vue.js. Features include application forms, candidate tracking, and club information.",
      confidential: true,
    },
  ];

  let benefits = [
    {
      name: "A self taught developer",
      description:
        "Someone who mostly learns through real projects, online resources, and hands-on experimentation. I've been to college but most of my skills come from self-learning and internships.",
    },
    {
      name: "A curious person",
      description:
        "Always exploring how things work and finding better ways to solve problems through coding and technology, which is the main reason why i chose to become a developer.",
    },
    {
      name: "A dedicated lifelong learner",
      description:
        "Continuously improving skills, experimenting with new tools, and staying updated with modern development trends. Currently focusing on mastering Laravel, learning Docker and Typescript.",
    },
  ];

  let experiences = [
    {
      title: "Web Developer Intern",
      place: "PT. Timedoor Indonesia",
      period: "September 2024 – February 2025",
      description:
        "Worked on internal systems using Laravel and Vue/Nuxt, built features, maintained production apps, and collaborated with the development team.",
    },
    {
      title: "Quality Assurance Intern",
      place: "PT. Timedoor Indonesia",
      period: "April 2025 – July 2025",
      description:
        "Performed manual testing & Automation testing using cypress, created test cases & documented bugs in Notion, and improved product stability by working closely with developers.",
    },
    {
      title: "Independent Freelance Web Developer",
      place: "Self-employed",
      period: "2024 — Present",
      description:
        "Worked directly with clients to build custom websites and systems using Laravel, Vue/Nuxt sometimes React or Svelte, and TailwindCSS. Handled full-cycle development including planning, design, development, and deployments.",
    },
    {
      title: "Freelance Developer",
      place: "Wedyapancer Dev",
      period: "April 2025 — Present",
      description:
        "Part of a developer group creating web, mobile, and desktop applications. Contributed to real client projects, API development, authentication systems, and UI implementation.",
    },
  ];

  let selectedWork = null;
</script>

<main class="flex flex-col flex-1 p-4">
  <section
    id="introPage"
    class="grid grid-cols-1 lg:grid-cols-2 gap-10 py-8 sm:py-14"
  >
    <div
      class="flex flex-col lg:justify-center text-center lg:text-left gap-6 md:gap-8 lg:gap-10"
    >
      <h2 class="font-semibold text-4xl sm:text-5xl md:text-6xl">
        Hi! I'm <span class="poppins text-blue-500">Pande</span> Praditya
        <br />
        <!-- This part types first -->
        <Typewriter {words} speed={80} startDelay={500} />
      </h2>

      <!-- The rest of your content remains the same -->
      <p class="text-base sm:text-lg md:text-xl">
        My <span class="text-blue-400">Favorite tech </span> includes PHP (Laravel),
        JS (Vue.js, Nuxt.js, SvelteKit), TailwindCSS, MySQL or PostgreSQL, and QA
        (Cypress).
      </p>
      <p class="text-base sm:text-lg md:text-xl">
        Besides the tech stack above, I'm also <span class="text-blue-400"
          >familiar</span
        > with AWS, Docker, and Git Actions.
      </p>
      <a
        href="mailto:johndoe@gmail.com"
        target="_blank"
        class="blueShadow mx-auto lg:mr-auto text-base sm:text-lg md:text-xl poppins relative overflow-hidden px-6 py-3 group rounded-full bg-white text-slate-950 cursor-pointer"
      >
        <div
          class="absolute top-0 right-full w-full h-full bg-blue-500 opacity-20 group-hover:translate-x-full z-0 duration-200"
        ></div>
        <h4 class="relative z-[9]">Get in touch &rarr;</h4>
      </a>
    </div>
    <div class="relative shadow-2xl grid place-items-center">
      <img
        src="/images/profile.webp"
        alt="Profile Image"
        class="object-cover z-[2] max-h-[70vh] rounded-full"
      />
    </div>
  </section>

  <section
    id="about"
    class="py-20 lg:py-32 flex flex-col gap-16 sm:gap-20 md:gap-24 relative"
  >
    <div class="flex flex-col gap-2 text-center py-4">
      <h6 class="text-lg sm:text-xl md:text-2xl">Want to know more?</h6>
      <h3 class="font-medium text-3xl sm:text-4xl md:text-5xl">
        A Bit <span class="poppins text-blue-500">about</span> me.
      </h3>
    </div>
    <p class="mx-auto poppins font-semibold text-lg sm:text-xl md:text-2xl">
      I am . . .
    </p>
    <div class="flex flex-col gap-20 w-full mx-auto max-w-[800px]">
      {#each benefits as benefit, index}
        <div class="flex gap-6 sm:gap-8">
          <p
            class="poppins text-4xl sm:text-5xl md:text-6xl text-slate-500 font-semibold"
          >
            0{index + 1}
          </p>
          <div class="flex flex-col gap-6 sm:gap-8">
            <h3 class="text-2xl sm:text-3xl md:text-5xl">
              {benefit.name}
            </h3>
            <p>{benefit.description}</p>
          </div>
        </div>
      {/each}
    </div>
  </section>

  <section id="projects" class="py-20 lg:py-32 flex flex-col gap-24">
    <div class="flex flex-col gap-2 text-center">
      <h4 class="text-lg sm:text-xl md:text-2xl">A few of my creations</h4>
      <h5 class="poppins font-semibold text-3xl sm:text-4xl md:text-5xl">
        Curious to <span class="poppins text-blue-500">see</span> my work?
      </h5>
    </div>
    <div class="grid grid-cols-1 lg:grid-cols-3 gap-12 lg:gap-10">
      <Work work={works[0]} on:preview={(e) => (selectedWork = e.detail)}>
        <p>
          Timedoor Inventory is an inventory management system with an
          integrated CMS for PT. Timedoor Indonesia built with <strong
            class="text-blue-500">Laravel</strong
          >
          and
          <strong class="text-blue-500">Nuxt.js</strong> with a
          <strong class="text-blue-500">TailwindCSS</strong> UI, hosted on
          <strong class="text-blue-500">AWS EC2!</strong>
          CRUD operations that allows employees to manage inventory data efficiently
          with a built in QR Code for easy access to specific items. It also features
          a register by admin approval that sends the user credentials through email.
        </p>
      </Work>
      <Work work={works[1]} on:preview={(e) => (selectedWork = e.detail)}>
        <p>
          Makardhi Jobfair is a job fair website for the Bali Tourism
          Polytechnic, built fully with <strong class="text-blue-500"
            >Laravel</strong
          >
          and
          <strong class="text-blue-500">TailwindCSS!</strong>
          It features job listings, company profiles, and an application system for
          students or public to apply directly through the platform.
        </p>
      </Work>
      <Work work={works[2]} on:preview={(e) => (selectedWork = e.detail)}>
        <p>
          Paskamras Recruitment is a recruitment website for candidates who want
          to join Paskamras, an event-organizing club at ITB STIKOM Bali. Built
          with
          <strong class="text-blue-500">Laravel</strong> and
          <strong class="text-blue-500">Vue.js!</strong>
          It features an application form, selection process updates, and information
          about Paskamras activities.
        </p>
      </Work>
    </div>
  </section>

  <section id="experience" class="py-20 lg:py-32 flex flex-col gap-20">
    <div class="flex flex-col gap-2 text-center">
      <h4 class="text-lg sm:text-xl md:text-2xl">My Journey</h4>
      <h5 class="poppins font-semibold text-3xl sm:text-4xl md:text-5xl">
        Work <span class="text-blue-500">Experience</span>
      </h5>
    </div>

    <div class="flex flex-col gap-14 mx-auto w-full max-w-[850px]">
      {#each experiences as exp, index}
        <div class="flex flex-col gap-4 border-l-4 border-blue-600 pl-6">
          <h3 class="text-2xl sm:text-3xl font-semibold">
            {exp.title}
          </h3>
          <p class="text-blue-500 font-medium">
            {exp.place} • <span class="text-slate-400">{exp.period}</span>
          </p>
          <p class="text-slate-300 leading-relaxed">
            {exp.description}
          </p>
        </div>
      {/each}
    </div>
  </section>
</main>

<!-- For work modal -->
{#if selectedWork}
  <div
    class="fixed px-4 inset-0 bg-black/70 backdrop-blur-sm flex items-center justify-center z-50"
  >
    <div
      class="bg-slate-900 p-6 rounded-xl max-w-3xl w-full h-[60vh] border border-blue-500 relative"
    >
      <!-- Close Button -->
      <button
        class="absolute top-3 right-3 text-slate-300 hover:text-white"
        on:click={() => (selectedWork = null)}
      >
        ✕
      </button>

      <!-- Title -->
      <h2 class="text-2xl font-semibold text-white mb-4">
        {selectedWork.name}
      </h2>

      <!-- Images -->
      {#if selectedWork.confidential}
        <div
          class="relative h-48 bg-slate-900 border border-gray-500 rounded-lg grid place-items-center text-gray-200"
        >
          <i
            class="fa-regular fa-face-frown absolute top-1/4 left-1/2 -translate-x-1/2 -translate-y-1/2 text-3xl"
          ></i>
          Preview unavailable due to contract with client.
        </div>
      {:else if selectedWork.images && selectedWork.images.length > 0}
        <div class="flex overflow-x-auto gap-4 pb-2">
          {#each selectedWork.images as img}
            <img
              src={img}
              alt={selectedWork.name}
              class="h-48 rounded-lg border border-slate-700 object-cover flex-shrink-0"
            />
          {/each}
        </div>
      {:else}
        <div
          class="h-48 bg-slate-800 border border-slate-700 rounded-lg grid place-items-center text-slate-400"
        >
          No preview available
        </div>
      {/if}

      <!-- Description -->
      <p class="mt-4 text-slate-300">
        {selectedWork.description || "This project has no description yet."}
      </p>
    </div>
  </div>
{/if}
