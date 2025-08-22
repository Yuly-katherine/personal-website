<template>
  <section class="text-white mt-18" id="skills">
    <div class="absolute right-0 top-[110rem] h-full w-full justify-end">
      <span class="flex opacity-20"
        ><span class="w-16 h-32 rounded-l-full flex bg-[#f59e0b] blur-2xl"></span
        ><span
          class="w-16 h-32 rounded-r-full flex bg-[#f88fc2] blur-2xl mt-14"
        ></span
      ></span>
    </div>
    <div
      class="md:grid md:grid-cols-2 gap-8 items-center py-8 px-4 xl:gap-16 xl:px-16"
    >
      <div class="mt-4 md:mt-0 text-left flex flex-col z-10 h-full w-[80%]">
        <h2 class="text-4xl font-bold text-white text-left mb-4">
          My
          <span
            class="text-transparent bg-clip-text bg-gradient-to-r from-[#f59e0b] to-[#ec4899]"
            >Skills</span
          >
        </h2>
        <div class="mt-8">
          <ul
            class="grid grid-cols-3 sm:grid-cols-4 gap-8 justify-items-center aos-init"
            data-aos="fade-up"
          >
            <li
              v-for="(skill, index) in skills"
              :key="index"
              class="flex flex-col items-center"
            >
              <div
                class="p-3 rounded-xl bg-[#111a3e] border border-[#1f1641] shadow-lg transition-transform duration-200 hover:scale-105"
              >
                <img :src="skill.icon" :alt="skill.name" class="w-14 h-14 object-contain" />
              </div>
              <span class="mt-2 text-sm text-gray-300">{{ skill.name }}</span>
            </li>
          </ul>
        </div>
      </div>
      <div data-aos="flip-right" class="mt-20 md:mt-0 aos-init aos-animate">
        <h2 class="text-4xl font-bold text-white text-left mb-4">
          My Education
        </h2>
           <div class="mt-8 space-y-4" data-aos="fade-up">
           <div
             v-for="(item, index) in education"
             :key="index"
             class="flex items-center rounded-xl p-4 bg-[#111a3e] shadow-lg border border-[#1f1641]"
           >
             <div class="w-1/4 flex justify-center">
               <img
                 src="https://img.icons8.com/ios-filled/100/ffffff/graduation-cap.png"
                 alt="graduation"
                 class="w-12 h-12"
               />
             </div>
             <div class="w-3/4 pl-4">
               <h3 class="text-lg font-semibold text-transparent bg-clip-text bg-gradient-to-r from-[#f59e0b] to-[#ec4899]">
                 {{ item.title }}
               </h3>
               <p class="text-white text-sm">{{ item.subtitle }}</p>
             </div>
           </div>
         </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const skills = [
  {
    name: 'HTML5',
    icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg'
  },
  {
    name: 'CSS3',
    icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg'
  },
  {
    name: 'JavaScript',
    icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg'
  },
  {
    name: 'TypeScript',
    icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg'
  },
  {
    name: 'Vue',
    icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg'
  },
  {
    name: 'Pinia',
    icon: 'https://pinia.vuejs.org/logo.svg'
  },
  {
    name: 'React',
    icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg'
  },
  {
    name: 'Tailwind',
    icon: 'https://www.vectorlogo.zone/logos/tailwindcss/tailwindcss-icon.svg'
  }
]

const education = [

  {
    title: "Course React.Js",
    subtitle: "Dec. 2022 - Coderhouse",
  },
  {
    title: "Web Developer",
    subtitle: "Aug. 2022 - Coderhouse",
  },
  {
    title: "Course JavaScript",
    subtitle: "Apr. 2022 - Coderhouse",
  },
  
  {
    title: "Course Vue.Js",
    subtitle: "Apr. 2021 - Platzi",
  },
  {
    title: "Electrical Engineering",
    subtitle: "Dec. 2016 - Antioquia University",
  },
];
</script>

<style scoped>
</style>