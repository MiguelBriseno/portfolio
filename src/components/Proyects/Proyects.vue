<template>
  <div class="bg-white py-24 sm:py-32" id="projects">
    <div class="mx-auto max-w-7xl px-6 lg:px-8">
      <div class="mx-auto max-w-4xl text-center">
        <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">
          Projects
        </h2>
        <p class="mt-2 text-lg leading-8 text-gray-600">
          Welcome to the "Projects" section of my portfolio! Here, you’ll find a
          curated selection of the projects I’ve developed, showcasing a range
          of skills and expertise in web development. Each project is a
          testament to my ability to tackle diverse challenges and create
          impactful solutions.
        </p>
      </div>
      <div
        class="mx-auto mt-16 grid max-w-2xl grid-cols-1 gap-x-8 gap-y-20 lg:mx-0 lg:max-w-none lg:grid-cols-3"
      >
        <article
          v-for="post in posts"
          :key="post.id"
          class="flex flex-col items-start justify-between"
        >
          <div class="relative w-full">
            <img
              :src="post.imageUrl"
              alt=""
              class="aspect-[16/9] w-full rounded-2xl bg-gray-100 object-cover sm:aspect-[2/1] lg:aspect-[3/2]"
            />
            <div
              class="absolute inset-0 rounded-2xl ring-1 ring-inset ring-gray-900/10"
            />
          </div>
          <div class="max-w-xl">
            <div class="mt-8 flex items-center gap-x-4 text-xs">
              <time :datetime="post.datetime" class="text-gray-500">{{
                post.date
              }}</time>
              <a
                :href="post.category.href"
                class="relative z-10 rounded-full bg-gray-50 px-3 py-1.5 font-medium text-gray-600 hover:bg-gray-100"
                >{{ post.category.title }}</a
              >
            </div>
            <div class="group relative">
              <h3
                class="mt-3 text-lg font-semibold leading-6 text-gray-900 group-hover:text-gray-600"
              >
                <a :href="post.href">
                  <span class="absolute inset-0" />
                  {{ post.title }}
                </a>
              </h3>
              <p class="mt-5 line-clamp-8 text-sm leading-6 text-gray-600">
                {{ post.description }}
              </p>
            </div>
          </div>
        </article>
      </div>
    </div>
  </div>
</template>
  
<script setup>
const posts = [
  {
    id: 1,
    title: "Azul ERP",
    href: "https://http.cat/status/301",
    description:
      "This is a comprehensive solution tailored specifically for the tequila industry, designed to provide a unified platform for managing all operational aspects. From expense control to sales order generation and detailed reporting, this system is built to enhance efficiency, accuracy, and strategic decision-making.",
    imageUrl: "https://i.postimg.cc/1RwywQHT/azul.jpg",
    date: "Feb 13, 2024",
    datetime: "2024-02-13",
    category: {
      title: "Vue.JS | NEST.JS | Axios | Tailwind",
      href: "https://vuejs.org/guide/introduction.html",
    },
  },
  {
    id: 2,
    title: "Oakland Ecommerce",
    href: "https://www.highpowerecommerce.com:8081",
    description:
      "We developed a Vue.js solution for a hardware companys sales force. This system streamlines order management, invoice downloading, balance inquiries, and payment processing, with full integration to SAP B1 for real-time updates.",
    imageUrl: "https://i.postimg.cc/1RVJYNQ4/oakland.jpg",
    date: "Mar 16, 2021",
    datetime: "2021-03-16",
    category: {
      title: "Vue.JS | NodeJS | C# | Vuetify | Axios",
      href: "https://vuejs.org/guide/introduction.html",
    },
  },
  {
    id: 3,
    title: "Softcarmel",
    href: "https://www.softcarmel.com",
    description:
      "At Softcarmel, we are committed to providing custom software development solutions tailored to meet the unique needs of each client. Our website is designed to facilitate communication and collaboration with our team of experts, as well as to showcase our portfolio of successful projects.",
    imageUrl: "https://i.postimg.cc/q75PjYFh/soft.jpg",
    date: "Dec 9, 2023",
    datetime: "2023-12-09",
    category: {
      title: "Vue.JS | Tailwind",
      href: "https://vuejs.org/guide/introduction.html",
    },
  },
  {
    id: 4,
    title: "Pokemon Pokédex",
    href: "https://http.cat/status/301",
    description:
      "Pokémon Explorer is an interactive web application that allows users to explore and discover detailed information about Pokémon using the public Pokémon API, PokeAPI. This application is designed to offer a user-friendly and educational experience for both Pokémon fans and developers interested in learning about API integration.",
    imageUrl: "https://i.postimg.cc/kXxw4Wjz/pokemon.jpg",
    date: "April 22, 2024",
    datetime: "2024-04-22",
    category: {
      title: "Vue.JS | Vuetify | Axios",
      href: "https://vuejs.org/guide/introduction.html",
    },
  },
  {
    id: 5,
    title: "Nasa App",
    href: "https://http.cat/status/301",
    description:
      "NASA Explorer is a web application designed to explore and visualize fascinating data provided by the NASA API. This application offers users an immersive experience to discover images, data, and other scientific information related to space, directly from NASA official resources.",
    imageUrl: "https://i.postimg.cc/qqyzxWk4/OIP.jpg",
    date: "Feb 19, 2024",
    datetime: "2024-02-19",
    category: {
      title: "Vue.JS | Vuetify",
      href: "https://vuejs.org/guide/introduction.html",
    },
  },
  {
    id: 6,
    title: "Jary Franco",
    href: "https://jaryoficial.com/",
    description:
      "In this project, I developed a dynamic and visually appealing website for Jary Franco, a prominent performer of regional Mexican music. Using HTML, CSS, and JavaScript, I created a comprehensive platform to offer an immersive and unique experience for both fans and the artist.",
    imageUrl: "https://i.postimg.cc/qM1FP6RK/jary.jpg",
    date: "Jun 28, 2021",
    datetime: "2021-06-28",
    category: {
      title: "HTML | CSS | JS | Mailchimp",
      href: "https://www.w3schools.com/",
    },
  },
];
</script>