<script>
  import Work from "./Work.svelte";
  import Typewriter from "./Typewriter.svelte";

  const words = [
    "Full-Stack Developer",
    "Quality Assurance",
    "Project Manager",
    "Problem Solver",
  ];

  let works = [
    {
      id: 1,
      name: "Timedoor Inventory",
      client: "PT. Timedoor Indonesia",
      period: "September 2024 - February 2025",
      tech: "Laravel + Nuxt.js",
      icon: "fa-solid fa-boxes-stacked",
      description:
        "Timedoor Inventory is an inventory management system with an integrated CMS for PT. Timedoor Indonesia. It is built in laravel with a register by admin approval that sends the user credentials through email. The frontend is built with Nuxt.js and TailwindCSS, hosted on AWS EC2. It features CRUD operations for managing inventory data efficiently, along with QR Code generation for easy access to specific items.",
      impact:
        "End-to-end delivery on a production internal system: Laravel API, Nuxt.js frontend and AWS EC2 deployment, built and maintained alongside the development team during my internship.",
      images: [
        "/images/works/work-1/landing-page.webp",
        "/images/works/work-1/login.webp",
        "/images/works/work-1/inquiries.webp",
        "/images/works/work-1/dashboard.webp",
      ],
      demo: true,
      url: false,
      confidential: false,
    },
    {
      id: 2,
      name: "Makardhi Jobfair",
      client: "Bali Tourism Polytechnic",
      period: "",
      tech: "Laravel + TailwindCSS",
      icon: "fa-solid fa-briefcase",
      description:
        "Makardhi Jobfair is a job fair website for Bali Tourism Polytechnic, built with Laravel Blade Template and TailwindCSS. It includes job listings, company profiles, and an application system for students and the public.",
      impact:
        "A public-facing platform that lets students and job seekers apply to listed companies directly, with the public site and the admin side served from one Laravel application.",
      images: [
        "/images/works/work-2/welcome.webp",
        "/images/works/work-2/landing-page.webp",
        "/images/works/work-2/login-admin.webp",
        "/images/works/work-2/admin-page.webp",
      ],
      demo: true,
      url: false,
      confidential: false,
    },
    {
      id: 3,
      name: "ABA Worldwide",
      client: "ABA Worldwide",
      period: "August 2025 - Present",
      tech: "Wordpress + Gutenberg",
      icon: "fa-solid fa-handshake",
      description:
        "ABA Worldwide is a company profile website for a local moving agency, built with Wordpress and Gutenberg. It features information about the company, services offered, and a contact form for inquiries, and Get a Quote form for potential clients to request a quote for relocation or freight services.",
      impact:
        "A live company profile for a working moving agency, where the contact and Get a Quote forms are the inbound path for relocation and freight enquiries.",
      images: [
        "/images/works/work-3/landing-page.webp",
        "/images/works/work-3/about-us.webp",
        "/images/works/work-3/moving-relocation.webp",
      ],
      demo: false,
      url: "https://abaworldwide.com",
      confidential: false,
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
      period: "September 2024 - February 2025",
      description:
        "Worked on internal systems using Laravel and Vue/Nuxt, built features, maintained production apps, and collaborated with the development team.",
    },
    {
      title: "Quality Assurance Intern",
      place: "PT. Timedoor Indonesia",
      period: "March 2025 - July 2025",
      description:
        "Performed manual testing & Automation testing using cypress, created test cases & documented bugs in Notion, and improved product stability by working closely with developers.",
    },
    {
      title: "Freelance Developer",
      place: "Wedyapancer Dev",
      period: "April 2025 - Present",
      description:
        "Part of a developer group creating web, mobile, and desktop applications. Contributed to real client projects, API development, authentication systems, and UI implementation.",
    },
    {
      title: "Junior Software Engineer",
      place: "ABA Worldwide",
      period: "August 2025 - Present",
      description:
        "Working as a junior software engineer at ABA Worldwide, contributing to the development and maintenance of their company profile website and operations app.",
    }
  ];

  let selectedWork = null;

  // for Image scroll indicator (its just so people know it can be scrolled, better UX)
  let imageContainer;
  let canScroll = false;

  function checkScroll() {
    if (imageContainer) {
      canScroll = imageContainer.scrollWidth > imageContainer.clientWidth;
    }
  }
</script>

<style>
  .hide-scrollbar {
    scrollbar-width: none; /* Firefox */
    -ms-overflow-style: none; /* IE/Edge */
  }
  .hide-scrollbar::-webkit-scrollbar {
    display: none; /* Chrome/Safari */
  }

  /* Modal scrollbar: dark enough to blend into the panel, still visible
     enough to show there is more content below. */
  .dark-scrollbar {
    scrollbar-width: thin;
    scrollbar-color: theme("colors.slate.700") transparent;
  }
  .dark-scrollbar::-webkit-scrollbar {
    width: 8px;
  }
  .dark-scrollbar::-webkit-scrollbar-button {
    display: none;
  }
  .dark-scrollbar::-webkit-scrollbar-track {
    background: transparent;
  }
  .dark-scrollbar::-webkit-scrollbar-thumb {
    background-color: theme("colors.slate.700");
    border-radius: 9999px;
  }
  .dark-scrollbar::-webkit-scrollbar-thumb:hover {
    background-color: theme("colors.slate.600");
  }
</style>

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
        My <span class="text-blue-400">Current tech stack </span> includes PHP (Laravel),
        JS (Vue.js, React.js, SvelteKit, Node.js), TailwindCSS, MySQL or PostgreSQL, and QA
        (Cypress).
      </p>
      <p class="text-base sm:text-lg md:text-xl">
        Besides the tech stack above, I'm also <span class="text-blue-400"
          >familiar</span
        > with AWS, Docker, Git Actions, Jenkins.
      </p>
      <a
        href="mailto:pandepraditya@gmail.com"
        target="_blank"
        class="blueShadow mx-auto lg:mr-auto text-base sm:text-lg md:text-xl poppins relative overflow-hidden px-6 py-3 group rounded-full bg-white text-slate-950 cursor-pointer"
      >
        <div
          class="absolute top-0 right-full w-full h-full bg-blue-500 opacity-20 group-hover:translate-x-full z-0 duration-200"
        ></div>
        <span class="relative z-[9]">Get in touch &rarr;</span>
      </a>
    </div>
    <div class="relative shadow-2xl grid place-items-center">
      <img
        aria-hidden="false"
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
      <p class="text-lg sm:text-xl md:text-2xl">Want to know more?</p>
      <h2 class="font-medium text-3xl sm:text-4xl md:text-5xl">
        A Bit <span class="poppins text-blue-500">about</span> me.
      </h2>
    </div>
    <p class="mx-auto poppins font-semibold text-lg sm:text-xl md:text-2xl">
      I am . . .
    </p>
    <div class="flex flex-col gap-20 w-full mx-auto max-w-[800px]">
      {#each benefits as benefit, index}
        <div class="flex gap-6 sm:gap-8 justify-between">
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
      <p class="text-lg sm:text-xl md:text-2xl">A few of my creations</p>
      <h2 class="poppins font-semibold text-3xl sm:text-4xl md:text-5xl">
        Curious to <span class="poppins text-blue-500">see</span> my work?
      </h2>
    </div>
    <div class="grid grid-cols-1 lg:grid-cols-3 gap-12 lg:gap-10">
      {#each works as work (work.id)}
        <Work {work} on:preview={(e) => (selectedWork = e.detail)} />
      {/each}
    </div>

    <!-- Closing entry: the three above are what I can show, not the limit -->
    <div
      class="p-4 sm:p-6 flex flex-col gap-4 rounded-lg border border-solid border-blue-700 text-center hover:border-blue-500 duration-200"
    >
      <div
        class="bg-slate-950 grid place-items-center px-4 text-5xl md:text-6xl -mt-10 sm:-mt-12 md:-mt-14 lg:-mt-16 mx-auto duration-200"
      >
        <i class="fa-regular fa-lightbulb" aria-hidden="true"></i>
      </div>
      <h3 class="font-medium text-xl sm:text-2xl md:text-3xl">
        . . . and any project you have in mind
      </h3>
      <p class="text-slate-300 max-w-[600px] mx-auto">
        These are the ones I can show publicly. If you have something else in
        mind, I would like to hear about it.
      </p>
      <a
        href="https://wa.me/628113866745?text=Hi%20Pande%2C%20I%20saw%20your%20portfolio%20and%20I%20have%20a%20project%20in%20mind."
        target="_blank"
        rel="noopener noreferrer"
        class="mx-auto mt-2 text-base sm:text-lg poppins relative overflow-hidden px-6 py-3 group rounded-full bg-white text-slate-950 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-blue-500"
      >
        <div
          class="absolute top-0 right-full w-full h-full bg-blue-500 opacity-20 group-hover:translate-x-full z-0 duration-200"
        ></div>
        <span class="relative z-[9]">
          <i class="fa-brands fa-whatsapp" aria-hidden="true"></i>
          Chat on WhatsApp &rarr;<span class="sr-only"> (opens in a new tab)</span>
        </span>
      </a>
      <p class="text-slate-400">
        or
        <a
          href="mailto:pandepraditya@gmail.com"
          class="underline duration-200 hover:text-blue-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-blue-500"
          >send an email</a
        >
      </p>
    </div>
  </section>

  <section id="experience" class="py-20 lg:py-32 flex flex-col gap-20">
    <div class="flex flex-col gap-2 text-center">
      <p class="text-lg sm:text-xl md:text-2xl">My Journey</p>
      <h2 class="poppins font-semibold text-3xl sm:text-4xl md:text-5xl">
        Work <span class="text-blue-500">Experience</span>
      </h2>
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
      class="bg-slate-900 p-6 rounded-xl max-w-3xl w-full h-[70vh] md:h-[60vh] overflow-y-auto dark-scrollbar border border-blue-500 relative"
    >
      <!-- Close Button -->
      <button
        class="absolute top-3 right-3 text-slate-300 hover:text-white"
        on:click={() => (selectedWork = null)}
      >
        ✕
      </button>

      <!-- Title -->
      <div class="mb-4">
        <h2 class="text-2xl font-semibold text-white">
          {selectedWork.name}
        </h2>
        {#if selectedWork.client}
          <p class="text-blue-500 font-medium">
            {selectedWork.client}
            {#if selectedWork.period}•{/if}
            <span class="text-slate-400">{selectedWork.period}</span>
          </p>
        {/if}
      </div>

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
        <div class="flex overflow-x-auto gap-4 pb-2 hide-scrollbar">
          {#each selectedWork.images as img}
            <img
              src={img}
              alt={selectedWork.name}
              class="h-48 rounded-lg border border-slate-700 object-cover flex-shrink-0"
            />
          {/each}
        </div>
        <p class="text-sm text-center text-slate-400">
          Shift + Scroll to view next images
        </p>
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

      <!-- What it actually achieved, modal only -->
      {#if selectedWork.impact}
        <div class="mt-4 p-4 rounded-lg border border-blue-700 bg-slate-950">
          <p class="flex items-center gap-2 text-blue-500 font-medium">
            <i class="fa-solid fa-bolt" aria-hidden="true"></i>
            Impact
          </p>
          <p class="mt-2 text-slate-300">{selectedWork.impact}</p>
        </div>
      {/if}

      {#if selectedWork.url}
        <a
          href={selectedWork.url}
          target="_blank"
          rel="noopener noreferrer"
          class="mt-4 w-1/2 flex items-center justify-between md:px-4 md:py-3.5 px-3 py-2.5 border border-slate-700 rounded-lg text-sm md:text-base font-medium text-white hover:border-slate-500 transition-colors"
        >
          <span class="flex items-center gap-2">
            <i class="fa-solid fa-globe text-blue-400"></i>
            {selectedWork.demo ? "View demo site" : "Visit website"}
          </span>
          <i class="fa-solid fa-arrow-right text-slate-500"></i>
        </a>
      {:else}
        <p class="mt-4 text-slate-400 border-t border-slate-700 pt-4">
          <span class="font-semibold">Notice:</span> Websites currently under maintenance or Not active anymore.
        </p>
      {/if}
    </div>
  </div>
{/if}
