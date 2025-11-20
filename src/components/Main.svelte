<script>
  import Work from "./Work.svelte";

  let works = [
    {
      name: "Timedoor Inventory",
      tech: "Laravel + Nuxt.js",
      icon: "fa-solid fa-boxes-stacked",
    },
    {
      name: "Makardhi Jobfair",
      tech: "Laravel + TailwindCSS",
      icon: "fa-solid fa-briefcase",
    },
    {
      name: "Paskamras Recruitment",
      tech: "Laravel + Vue.js",
      icon: "fa-solid fa-handshake",
    },
  ];

  let benefits = [
    {
      name: "A self-taught developer",
      description:
        "Someone who learns independently through real projects, online resources, and hands-on experimentation.",
    },
    {
      name: "A curious problem-solver",
      description:
        "Always exploring how things work and finding efficient, practical solutions to challenges.",
    },
    {
      name: "A dedicated lifelong learner",
      description:
        "Continuously improving skills, experimenting with new tools, and staying updated with modern development trends.",
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
      period: "March 2025 — Present",
      description:
        "Part of a developer group creating web, mobile, and desktop applications. Contributed to real client projects, API development, authentication systems, and UI implementation.",
    },
  ];
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
        Hi! I'm <span class="poppins text-violet-400">Pande</span> Praditya
        <br />
        Software
        <span class="poppins text-violet-400">Developer</span>
      </h2>
      <p class="text-base sm:text-lg md:text-xl">
        My <span class="text-violet-400">Favorite tech </span> includes PHP (Laravel),
        JS (Vue.js, Nuxt.js, SvelteKit), TailwindCSS, MySQL or PostgreSQL, and QA
        (Cypress)
      </p>
      <a
        href="mailto:pandepraditya@gmail.com"
        target="_blank"
        class="blueShadow mx-auto lg:mr-auto text-base sm:text-lg md:text-xl poppins relative overflow-hidden px-6 py-3 group rounded-full bg-white text-slate-950 cursor-pointer"
      >
        <div
          class="absolute top-0 right-full w-full h-full bg-violet-400 opacity-20 group-hover:translate-x-full z-0 duration-200"
        ></div>
        <h4 class="relative z-[9]">Get in touch &rarr;</h4>
      </a>
    </div>
    <div class="relative shadow-2xl gird place-items-center">
      <img
        src={"images/profile.png"}
        alt="Profile Image"
        class="object-cover z-[2] max-h-[70vh]"
      />
    </div>
  </section>

  <section
    id="about"
    class="py-20 lg:py-32 flex flex-col gap-16 sm:gap-20 md:gap-24 relative"
  >
    <div
      class="flex flex-col gap-2 text-center py-4"
    >
      <h6 class="text-lg sm:text-xl md:text-2xl">Want to know more?</h6>
      <h3 class="font-medium text-3xl sm:text-4xl md:text-5xl">
        A Bit <span class="poppins text-violet-400">about</span> me.
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
        Curious to <span class="poppins text-violet-400">see</span> my work?
      </h5>
    </div>
    <div class="grid grid-cols-1 lg:grid-cols-3 gap-12 lg:gap-10">
      <Work work={works[0]}>
        <p>
          Timedoor Inventory is an inventory management system with an
          integrated CMS for PT. Timedoor Indonesia built with <strong
            class="text-violet-400">Laravel</strong
          >
          and
          <strong class="text-violet-400">Nuxt.js</strong> with a
          <strong class="text-violet-400">TailwindCSS</strong> UI, hosted on
          <strong class="text-violet-400">AWS EC2!</strong>
          CRUD operations that allows employees to manage inventory data efficiently
          with a built in QR Code for easy access to specific items.
        </p>
      </Work>
      <Work work={works[1]}>
        <p>
          Makardhi Jobfair is a job fair website for the Bali Tourism
          Polytechnic, built fully with <strong class="text-violet-400"
            >Laravel</strong
          >
          and
          <strong class="text-violet-400">TailwindCSS!</strong>
          It features job listings, company profiles, and an application system for
          students or public to apply directly through the platform.
        </p>
      </Work>
      <Work work={works[2]}>
        <p>
          Paskamras Recruitment is a recruitment website for candidates who want
          to join Paskamras, an event-organizing club at ITB STIKOM Bali. Built
          with
          <strong class="text-violet-400">Laravel</strong> and
          <strong class="text-violet-400">Vue.js!</strong>
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
        Work <span class="text-violet-400">Experience</span>
      </h5>
    </div>

    <div class="flex flex-col gap-14 mx-auto w-full max-w-[850px]">
      {#each experiences as exp, index}
        <div class="flex flex-col gap-4 border-l-4 border-violet-500 pl-6">
          <h3 class="text-2xl sm:text-3xl font-semibold">
            {exp.title}
          </h3>
          <p class="text-violet-400 font-medium">
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
