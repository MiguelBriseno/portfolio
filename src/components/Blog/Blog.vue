<template>
    <div class="bg-white py-24 sm:py-32" id="blog">
      <div class="mx-auto max-w-7xl px-6 lg:px-8">
        <div class="mx-auto max-w-2xl lg:max-w-4xl">
          <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">From the blog</h2>
          <p class="mt-2 text-lg leading-8 text-gray-600">Explore a diverse range of topics, from technology and artificial intelligence to sports, astrology, and my love for dogs. On the blog, I share insights and reflections to inspire and entertain those eager to learn something new.</p>
          <div class="mt-16 space-y-20 lg:mt-20 lg:space-y-20">
            <article v-for="post in posts" :key="post.id" class="relative isolate flex flex-col gap-8 lg:flex-row">
              <div class="relative aspect-[16/9] sm:aspect-[2/1] lg:aspect-square lg:w-64 lg:shrink-0">
                <img :src="post.imageUrl" alt="" class="absolute inset-0 h-full w-full rounded-2xl bg-gray-50 object-cover" />
                <div class="absolute inset-0 rounded-2xl ring-1 ring-inset ring-gray-900/10" />
              </div>
              <div>
                <div class="flex items-center gap-x-4 text-xs">
                  <time :datetime="post.datetime" class="text-gray-500">{{ post.date }}</time>
                  <a :href="post.category.href" class="relative z-10 rounded-full bg-gray-50 px-3 py-1.5 font-medium text-gray-600 hover:bg-gray-100">{{ post.category.title }}</a>
                </div>
                <div class="group relative max-w-xl">
                  <h3 class="mt-3 text-lg font-semibold leading-6 text-gray-900 group-hover:text-gray-600">
                    <a :href="post.href">
                      <span class="absolute inset-0" />
                      {{ post.title }}
                    </a>
                  </h3>
                  <p class="mt-5 text-sm leading-6 text-gray-600">{{ post.description }}</p>
                </div>
                <div class="mt-6 flex border-t border-gray-900/5 pt-6">
                  <div class="relative flex items-center gap-x-4">
                    <img :src="post.author.imageUrl" alt="" class="h-10 w-10 rounded-full bg-gray-50" />
                    <div class="text-sm leading-6">
                      <p class="font-semibold text-gray-900">
                        <a :href="post.author.href">
                          <span class="absolute inset-0" />
                          {{ post.author.name }}
                        </a>
                      </p>
                      <p class="text-gray-600">{{ post.author.role }}</p>
                    </div>
                  </div>
                </div>
              </div>
            </article>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  const posts = [
    {
      id: 1,
      title: 'From Crisis to Recovery: My Experience as an IT Manager During a Hack',
      href: 'https://dly.to/JoBwgMXtwgG',
      description:
        'Experiencing a ransomware attack is every IT professionals worst nightmare. In this blog post, I’ll share the gripping story of how we faced BlackHunt, a notorious ransomware, and the steps we took to recover and secure our operations. From the initial breach to our comprehensive recovery strategy, learn how we turned a crisis into a lesson for future resilience.',
      imageUrl:
        'https://i.postimg.cc/1zq7Sbqh/hacker.jpg',
      date: 'August 22, 2024',
      datetime: '2024-08-22',
      category: { title: 'Ransomware', href: 'https://dly.to/JoBwgMXtwgG' },
      author: {
        name: 'Miguel Briseño',
        role: 'Softcarmel / Co-Founder',
        href: 'https://www.softcarmel.com',
        imageUrl:
          'https://i.postimg.cc/VvdFcFzh/perfil.png',
      },
    },
  ]
  </script>