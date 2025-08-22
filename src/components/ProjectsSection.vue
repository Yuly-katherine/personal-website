<template>
  <section class="text-white mt-20" id="projects">
    <div class="px-4 xl:pl-16">
      <div class="mb-4 md:flex md:justify-between xl:pr-16">
        <h2 class="text-4xl font-bold text-white">My Projects</h2>
      </div>
      <ul
        class="px-4 sm:py-16 xl:pr-16 grid grid-cols-1 gap-6 pt-10 sm:grid-cols-2 md:gap-10 md:pt-12 lg:grid-cols-3 aos-init"
        data-aos="fade-right"
      >
        <div v-for="card in cards" :key="card.name">
          <div
            class="h-52 md:h-[24rem] rounded-t-xl relative group"
            :style="{backgroundImage:'url('+card.img+')', backgroundSize:'cover'}"
          >
            <div
              class="overlay items-center justify-center absolute top-0 left-0 w-full h-full bg-[#181818] bg-opacity-0 hidden group-hover:flex group-hover:bg-opacity-80 transition-all duration-500"
            >
              <a
                class="h-14 w-14 mr-2 border-2 relative rounded-full border-[#ADB7BE] hover:border-white group/link" target="_blank"
                :href="card.github"
                ><svg
                  xmlns="http://www.w3.org/2000/svg"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke-width="1.5"
                  stroke="currentColor"
                  aria-hidden="true"
                  data-slot="icon"
                  class="h-10 w-10 text-[#ADB7BE] absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 cursor-pointer group-hover/link:text-white"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    d="M17.25 6.75 22.5 12l-5.25 5.25m-10.5 0L1.5 12l5.25-5.25m7.5-3-4.5 16.5"
                  ></path></svg></a
              ><a
                class="h-14 w-14 border-2 relative rounded-full border-[#ADB7BE] hover:border-white group/link" target="_blank"
                :href="card.link"
                ><svg
                  xmlns="http://www.w3.org/2000/svg"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke-width="1.5"
                  stroke="currentColor"
                  aria-hidden="true"
                  data-slot="icon"
                  class="h-10 w-10 text-[#ADB7BE] absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 cursor-pointer group-hover/link:text-white"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    d="M2.036 12.322a1.012 1.012 0 0 1 0-.639C3.423 7.51 7.36 4.5 12 4.5c4.638 0 8.573 3.007 9.963 7.178.07.207.07.431 0 .639C20.577 16.49 16.64 19.5 12 19.5c-4.638 0-8.573-3.007-9.963-7.178Z"
                  ></path>
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    d="M15 12a3 3 0 1 1-6 0 3 3 0 0 1 6 0Z"
                  ></path></svg
              ></a>
            </div>
          </div>
          <div
            class="text-white rounded-b-xl mt-3 bg-[#111a3e] shadow-lg border border-[#1f1641] py-6 px-4"
          >
            <h3 class="text-lg font-semibold uppercase lg:text-xl">
              {{ card.name }}
            </h3>
            <p class="text-[#ADB7BE]">
              {{ card.description }}
            </p>
            <div class="flex flex-wrap p-2.5">
              <div v-for="technology in card.technologies" :key="technology"
                class="text-center ml-1 mt-1 rounded-3xl bg-[#111827]"
                style="
                  box-shadow: rgba(0, 0, 0, 0.1) 0px 4px 30px;
                  border: 1px solid rgb(17, 24, 39);
                  backdrop-filter: blur(9px);
                "
              >
                <p class="px-1 py-2">{{ technology }}</p>
              </div>
            </div>
          </div>
        </div>
      </ul>
    </div>
  </section>
</template>

<script  setup >
//----------IMPORTS----------//
import { ref } from "vue";

//----------VARIABLES----------//
const cards = ref([
  {
    name: "Burger Ecommerce",
    description:
      "Burger Chips is a hamburger store built with React that allows users to view the full menu, and add products to a shopping cart. The application enables real-time cart management, offering a smooth and interactive experience. All data such as products is stored and managed using Firebase.",
    img: "burgerChips.png",
    alt:"BurgerEcommerce",
    technologies: ['React', 'JavaScript', 'Firebase'],
    github:"https://github.com/Yuly-katherine/Burguer-Eccomerce",
    link: "https://yuly-katherine.github.io/Burguer-Eccomerce/"
  },
  {
    name: "MultiStep Form",
    description:
      "This project is a three-step form built with Vue 3, TypeScript, Yup, and Tailwind CSS. The user must complete all required fields in each step before proceeding. Upon completion and submission, a confirmation modal is displayed, indicating that the data was successfully sent.",
    img: "MultiStepForm.png",
    alt:"MultiStepForm",
    technologies: ['Vue', 'TypeScript', 'Tailwind CSS'],
    github:"https://github.com/Yuly-katherine/multiStep-form",
    link: "https://yuly-katherine.github.io/multiStep-form/"
  },
  {
    name: "Favorite Pokemon",
    description:
      "Pokedex is a web application built with Vue that allows users to explore a list of Pokemons, view detailed information about each one and mark their favorites. It includes a filter to show only favorite Pokemon, improving user interaction. The project also integrates Vitest for unit testing, ensuring reliable and maintainable code.",
    img: "pokedex.png",
    alt:"favoritePokemon",
    technologies: ['Vue', 'JavaScript'],
    github:"https://github.com/Yuly-katherine/pokedex-app",
    link: "https://yuly-katherine.github.io/pokedex-app/"
  },
]);
</script>
