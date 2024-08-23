<template>
  <div class="bg-white py-24 sm:py-32" id="blog">
    <div class="mx-auto max-w-7xl px-6 lg:px-8">
      <div class="mx-auto max-w-2xl lg:max-w-4xl">
        <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">
          From the blog
        </h2>
        <p class="mt-2 text-lg leading-8 text-gray-600">
          Explore a diverse range of topics, from technology and artificial
          intelligence to sports, astrology, and my love for dogs. On the blog,
          I share insights and reflections to inspire and entertain those eager
          to learn something new.
        </p>
        <div class="mt-16 space-y-20 lg:mt-20 lg:space-y-20">
          <article
            v-for="post in posts"
            :key="post.id"
            class="relative isolate flex flex-col gap-8 lg:flex-row cursor-pointer"
            @click="showModal(post)"
          >
            <div
              class="relative aspect-[16/9] sm:aspect-[2/1] lg:aspect-square lg:w-64 lg:shrink-0"
            >
              <img
                :src="post.imageUrl"
                alt=""
                class="absolute inset-0 h-full w-full rounded-2xl bg-gray-50 object-cover"
              />
              <div
                class="absolute inset-0 rounded-2xl ring-1 ring-inset ring-gray-900/10"
              />
            </div>
            <div>
              <div class="flex items-center gap-x-4 text-xs">
                <time :datetime="post.datetime" class="text-gray-500">{{
                  post.date
                }}</time>
                <a
                  class="relative z-10 rounded-full bg-gray-50 px-3 py-1.5 font-medium text-gray-600 hover:bg-gray-100"
                  >{{ post.category.title }}</a
                >
              </div>
              <div class="group relative max-w-xl">
                <h3
                  class="mt-3 text-lg font-semibold leading-6 text-gray-900 group-hover:text-gray-600"
                >
                  <a>
                    <span class="absolute inset-0" />
                    {{ post.title }}
                  </a>
                </h3>
                <p class="mt-5 line-clamp-5 text-sm leading-6 text-gray-600">
                  {{ post.description }}
                </p>
              </div>
              <div class="mt-6 flex border-t border-gray-900/5 pt-6">
                <div class="relative flex items-center gap-x-4">
                  <img
                    :src="post.author.imageUrl"
                    alt=""
                    class="h-10 w-10 rounded-full bg-gray-50"
                  />
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

    <!-- Modal Component -->
    <BlogPostModal
      :open="modalOpen"
      :post="selectedPost"
      @close="handleClose"
    />
  </div>
</template>

<script setup>
import { ref } from "vue";
import BlogPostModal from "../Modal/Modal.vue";

const posts = [
  {
    id: 1,
    title:
      "From Crisis to Recovery: My Experience as an IT Manager During a Hack",
    href: "https://dly.to/JoBwgMXtwgG",
    description: `The incident began on a Friday, shortly after the New Year. During my routine database backup at 8:00 PM, I noticed that the wallpaper of the main server had been replaced with the BlackHunt ransomware logo, known for its destructive impact.
    Immediately, I conducted an infrastructure assessment to identify and quarantine the compromised servers. Given the failure to recover the decryption keys, the strategic decision was made to format the affected server and reconfigure it from scratch using available database backups. Simultaneously, the development team was tasked with rebuilding the Docker containers necessary to restore our in-house web applications.
    To contain the ransomware’s spread, we engaged a cybersecurity firm to deploy an endpoint protection solution. SentinelOne was recommended. I coordinated the IT team to install the endpoint across all company assets at our offices and distribution centers. After 24 hours of implementation and securing the assets with SentinelOne, we activated the recovery plan based on the backups.
    We contacted our SAP provider to obtain the hardware key required to reinstall SAP B1, the ERP system used by the company. The infrastructure team defined the technical requirements and configured the new server. After 48 hours of intensive work, we were able to resume operations. However, we experienced a loss of one day’s worth of data as the shadow copies of the operating system were deleted, leaving us with only the backups stored on AWS.
    On Monday, as operations resumed, I convened an urgent meeting with department heads to present a recovery plan. This plan involved virtually replicating transactions based on copies of invoices and movements from the day of the attack. After an additional 72 hours of coordinated effort, we successfully restored normal operations.
    In the post-incident phase, we conducted internal and external audits, implemented new security protocols, and provided staff training. We learned that the ransomware had entered through an apparently innocuous email. As Freddy Vega, CEO of Platzi, aptly states, “Your company is only as strong as its weakest link.”`,
    imageUrl: "https://i.postimg.cc/1zq7Sbqh/hacker.jpg",
    date: "August 22, 2024",
    datetime: "2024-08-22",
    category: {
      title: "Ransomware",
      href: "https://dly.to/JoBwgMXtwgG",
    },
    author: {
      name: "Miguel Briseño",
      role: "Softcarmel / Co-Founder",
      href: "https://www.softcarmel.com",
      imageUrl: "https://i.postimg.cc/VvdFcFzh/perfil.png",
    },
  },
  {
    id: 2,
    title: "The Nerves That Opened the Door to My Development Career",
    href: "https://dly.to/5IqPn7lyp55",
    description: `I remember the day of my first interview for a junior frontend developer position like it was yesterday. I had spent weeks preparing—reviewing JavaScript concepts, brushing up on HTML and CSS, and doing online exercises. But nothing could really prepare me for the nerves I felt that day.
    The interview was at a small tech company that was rapidly growing. I knew this opportunity could be my entry into the professional world of development, and that only added to the pressure. I arrived early, portfolio in hand, trying to keep calm while waiting in the reception area.
    When they finally called me in, my heart was racing. The interviewer, a senior developer with years of experience, greeted me with a friendly smile, which helped to calm me down a bit. He asked me some questions about my experience, the projects I had worked on, and how I tackled technical challenges.
    At first, my answers came out a bit awkward, broken up by nerves. But as the interview progressed, I started to relax. When he asked me to solve a small coding exercise, the nerves hit me again, but this time, I decided to focus on what I knew. I took a deep breath and started working.
    The exercise wasn’t easy, but I managed to stay calm and think through the solution step by step. When I finished, I explained my reasoning, and to my surprise, the interviewer nodded in approval. After that, the interview felt more like a conversation between colleagues than an interrogation.
    At the end, the interviewer thanked me for my time and said they would be in touch. I walked out of the office feeling exhausted but also proud of myself for overcoming my nerves and giving it my best shot.
    A few days later, I received a call that changed my life. They offered me the job. I couldn’t believe it. Despite the nerves and insecurities, I had landed my first job as a junior frontend developer. That moment marked the beginning of my professional career, and I’ll always remember how important it was to learn to handle pressure and trust in my abilities, even when the nerves tried to get the best of me.`,
    imageUrl: "https://i.postimg.cc/QNJmS40x/pexels-sora-shimazaki-5668858.jpg",
    date: "August 22, 2024",
    datetime: "2024-08-22",
    category: {
      title: "Interview",
      href: "https://dly.to/5IqPn7lyp55",
    },
    author: {
      name: "Miguel Briseño",
      role: "Softcarmel / Co-Founder",
      href: "https://www.softcarmel.com",
      imageUrl: "https://i.postimg.cc/VvdFcFzh/perfil.png",
    },
  },
  {
    id: 3,
    title:
      "The Moment That Changed My Life and Drove Me to Start My Own Business",
    href: "https://dly.to/ElfpMyjdtQO",
    description: `I’ll never forget the day I found out I was going to be a dad. I was at home after a long day of work, going through some emails when my partner walked into the room with a smile that said more than words ever could. She handed me a small box, and when I opened it, I found a tiny pair of baby shoes and a positive pregnancy test.
    My mind went blank for a second, and then a wave of excitement, joy, and, yes, a little fear, washed over me. Becoming a dad was something I had always wanted, but at that moment, the reality of what it meant began to sink in. I knew that I wasn’t just going to be responsible for my own life anymore, but also for a little one who would depend on me for everything.
    That night, as I lay in bed, I couldn’t stop thinking about the future. I wanted to make sure my child had everything they needed—not just love and care, but also the financial stability to grow up without worries. That’s when the idea that would change my professional life began to take shape.
    I had been toying with the idea of starting my own business for a while, but I had never taken the leap. Now, though, I had a powerful reason to do it. I wanted to create something of my own, something that would give me control over my time and income, but also offer the opportunity to build a legacy for my family. And so, the idea to start my own software development company was born.
    The following months were intense. While my partner and I prepared for the baby’s arrival, I also immersed myself in planning and developing my business. It wasn’t easy; there were many challenges and moments of doubt, but every time I thought about my child’s future, I found the motivation I needed to keep going.
    Eventually, I launched my company, “Softcarmel.” Although the first few months were tough, the reward of knowing I was building something for my family made every sacrifice worth it. Now, every time I look at my child, I know that deciding to start my own business was the right choice. Not only for the financial stability I’ve achieved but because I’m teaching them by example that, with hard work and dedication, it’s possible to create the future you want.`,
    imageUrl: "https://i.postimg.cc/YCYhfVzd/pexels-kseniachernaya-3952022.jpg",
    date: "August 22, 2024",
    datetime: "2024-08-22",
    category: {
      title: "Personal",
      href: "https://dly.to/ElfpMyjdtQO",
    },
    author: {
      name: "Miguel Briseño",
      role: "Softcarmel / Co-Founder",
      href: "https://www.softcarmel.com",
      imageUrl: "https://i.postimg.cc/VvdFcFzh/perfil.png",
    },
  },
  {
    id: 4,
    title: "The Day the Code Made Us Winners",
    href: "https://dly.to/Zj0tlOsvE8N",
    description: `It was during my last year at the University of Guadalajara, on the CUValles campus. After countless late nights filled with code and coffee, Daniel and I decided to enter the university’s programming contest. It was one of those competitions that make your nerves go wild, but honestly, we were excited.
    I remember the day of the event; we arrived early, loaded with water bottles and snacks, ready for anything. We were assigned a table in the auditorium, where other teams were already setting up, and the room buzzed with the sound of keyboards and hushed conversations. Daniel looked at me with that unwavering confidence of his and said, “Today is our day.”
    The challenge was to solve several problems within a limited time, each one more complex than the last. We had to apply everything we knew: algorithms, data structures, and that ability to think outside the box that had saved us so many times before. The first hour flew by, and we managed to solve the initial problems without much trouble. But the third problem was a real headache. We were stuck on it for nearly an hour, and at one point, I admit we almost gave up.
    But then, something clicked. Between the two of us, we came up with a clever solution, and when we finally ran the code and it worked, the relief was immense. We knew there was still much to do, but that small victory gave us the boost we needed. From that point on, everything flowed.
    Time ran out, and we submitted our solutions. We didn’t know what to expect, but we were satisfied with our effort. When they announced the winners, my heart was pounding. And then, we heard our names: “Miguel Briseño and Daniel Montes.” We couldn’t believe it. We looked at each other, stunned, and then got up to receive the prize. It was a surreal moment, but above all, it was confirmation that all those hours of hard work and learning had paid off.
    Even now, when we get together to reminisce, that story always comes up. It’s one of those anecdotes that reminds us why we love what we do so much and how, with a little perseverance, great things can be achieved.`,
    imageUrl: "https://i.postimg.cc/B6xgrM3p/pexels-pavel-danilyuk-5496464.jpg",
    date: "August 22, 2024",
    datetime: "2024-08-22",
    category: {
      title: "Software | Code",
      href: "https://dly.to/Zj0tlOsvE8N",
    },
    author: {
      name: "Miguel Briseño",
      role: "Softcarmel / Co-Founder",
      href: "https://www.softcarmel.com",
      imageUrl: "https://i.postimg.cc/VvdFcFzh/perfil.png",
    },
  },
];
const modalOpen = ref(false);
const selectedPost = ref(null);

function showModal(post) {
  selectedPost.value = post;
  modalOpen.value = true;
}

function handleClose() {
  modalOpen.value = false;
}
</script>
