<script setup lang="ts">
// TODO: Add GitHub link with icon
// TODO: Add LinkedIn lnk with icon

import { format } from "date-fns";
import Divider from "./components/Divider.vue";
import EnvelopeIcon from "./components/EnvelopeIcon.vue";
import GitHubIcon from "./components/GitHubIcon.vue";
import Heading from "./components/Heading.vue";
import LinkIcon from "./components/LinkIcon.vue";

const formatDate = (date: Date) => format(date, "LLL y");

const languages = [
  "JavaScript (ES6)",
  "TypeScript",
  "Node.js",
  "HTML5",
  "CSS3",
  "PHP",
  "SQL",
  "Python",
];

const frameworks = [
  "React",
  "React Native",
  "Vue",
  "GraphQL",
  "Express",
  "Laravel",
];

const technologies = ["Jest", "Chai", "Mocha", "Cypress", "Git", "CircleCI"];

const databases = ["MySQL", "PostgreSQL", "MongoDB", "SQLite", "Redis"];

const skills: { title: string; children: string[] }[] = [
  { title: "Languages", children: [...languages] },
  { title: "Technologies", children: [...frameworks, ...technologies] },
  { title: "Databases", children: [...databases] },
];

const experiece: {
  company: string;
  startDate: Date;
  endDate: Date;
  position: string;
  bulletPoints: string[];
  technologies: string[];
}[] = [
  {
    company: "Cliengo",
    position: "Back-End Developer",
    startDate: new Date(2021, 8, 0),
    endDate: new Date(2022, 3, 0),
    bulletPoints: [
      `Developed custom features for a Chatbot and helped several clients who had different needs for their business to bring a better customer service with their Chatbot`,
    ],
    technologies: ["Node.js", "AWS Lambdas", "API Gateway"],
  },

  {
    company: "Ordde S.A",
    position: "Full-stack Web Developer",
    startDate: new Date(2021, 1, 0),
    endDate: new Date(2021, 8, 0),
    bulletPoints: [
      "Contributed to the development of a large application. Here I had the opportunity to work with a team and learned how they work together. I quickly adapted to their workflow and their tech stack which allow me to start adding new features in a couple of weeks.",
    ],
    technologies: ["JavaScript", "Meteor JS", "MongoDB", "CircleCI"],
  },

  {
    company: "Workana",
    position: "Freelancer",
    startDate: new Date(2020, 3, 0),
    endDate: new Date(2021, 1, 0),
    bulletPoints: [
      "Completed successfully several projects receiving excellent qualification from my clients.",
      "All my projects are related with JavaScript and\or PHP",
      "Working as freelancer have improved my communication and adaptability skills, valuable skills in this industry.",
    ],
    technologies: ["JavaScript", "Vue", "PHP", "Laravel"],
  },

  {
    company: "System Click s.a",
    position: "Junior Software Developer ",
    startDate: new Date(2017, 10, 0),
    endDate: new Date(2019, 12, 0),
    bulletPoints: [
      "Collaborated in the development of new products such as Administrative Software, Desktop Applications, CMS and Web Sites, acquiring solid experience on the field.",
    ],
    technologies: ["JavaScript", "Vue", "Electron", "MongoDB", "PostgreSQL"],
  },
];

const certifications: {
  title: string;
  emitter: string;
  url: string;
  date: Date;
}[] = [
  {
    title: "Machine Learning",
    emitter: "Coursera",
    date: new Date(2021, 8, 0),
    url: "https://www.coursera.org/account/accomplishments/verify/YNUELBFRPXER",
  },

  {
    title: "Natural Language Processing with Classification and Vector Spaces",
    emitter: "Coursera",
    date: new Date(2021, 10, 0),
    url: "https://www.coursera.org/account/accomplishments/certificate/452UQT3FUFGM",
  },

  {
    title:
      "Divide and Conquer, Sorting and Searching, and Randomized Algorithms",
    emitter: "Coursera",
    date: new Date(2021, 11, 0),
    url: "https://www.coursera.org/account/accomplishments/verify/9C9T4CXA4DXK",
  },

  {
    title: "APIs and Microservices",
    emitter: "freeCodeCamp",
    date: new Date(2021, 7, 0),
    url: "https://freecodecamp.org/certification/diegodasilva/apis-and-microservices",
  },

  {
    title: "JavaScript Algorithms and Data Structures",
    emitter: "freeCodeCamp",
    date: new Date(2022, 5, 0),
    url: "https://freecodecamp.org/certification/diegodasilva/javascript-algorithms-and-data-structures",
  },
];

const projects: {
  name: string;
  excerpt: string;
  website?: string;
  github: string;
}[] = [
  {
    name: "Liboards",
    excerpt:
      "An Issue Tracker made with React and GraphQL, written in TypeScript.",
    website: "https://liboards.space",
    github: "https://github.com/smartcrash/liboards",
  },

  {
    name: "Another TODO List",
    excerpt:
      "A simple and beautiful TODO list app made with React and GraphQL, written in TypeScript.",
    github: "https://github.com/smartcrash/another-todo-list",
  },
];

const links: { label: string; url: string }[] = [
  { label: "GitHub", url: "https://github.com/smartcrash" },
  {
    label: "LinkedIn",
    url: "https://linkedin.com/in/diego-da-silva-developer",
  },
  {
    label: "Workana",
    url: "https://workana.com/freelancer/93bb3861a382b4baacb8ca8ef792a426",
  },
];
</script>

<template>
  <main
    class="mx-auto text-gray-700 space-y-5 px-10 pt-5"
    :style="{ maxWidth: '1200px' }"
  >
    <section class="text-center -mb-5 relative">
      <h1 class="text-6xl font-mono font-black tracking-tighter">
        Diego Da'Silva
      </h1>
      <h5 class="space-x-3 mt-5">
        <span>Full-Stack Software Developer</span>
        <span>|</span>
        <span
          ><a href="mailto:smartcrashomg@gmail.com" class="underline">
            <EnvelopeIcon />
            smartcrashomg@gmail.com</a
          >
        </span>

        <span>|</span>
        <span>English and Spanish speaker</span>
      </h5>
    </section>

    <section>
      <Heading>Skills</Heading>

      <Divider />

      <dl class="grid grid-cols-8 gap-1">
        <template v-for="{ title, children } in skills">
          <dt>
            <h6 class="font-bold">{{ title }}:</h6>
          </dt>
          <dd class="col-span-7">
            <ul class="flex flex-wrap">
              <li v-for="(child, index) in children" class="flex">
                {{ child }}
                <span v-if="index < children.length - 1" class="mx-2">•</span>
              </li>
            </ul>
          </dd></template
        >
      </dl>
    </section>

    <section>
      <Heading>Professional Experience</Heading>

      <Divider />

      <ul class="space-y-3 overflow-hidden">
        <li
          v-for="{
            company,
            position,
            startDate,
            endDate,
            bulletPoints,
            technologies,
          } in experiece"
        >
          <article class="relative pl-10">
            <span class="flex col-span-2 items-center absolute top-1 left-0">
              <svg viewBox="0 0 12 12" class="w-3 h-3 mr-6 overflow-visible">
                <circle cx="6" cy="6" r="6" fill="currentColor"></circle>
                <path
                  d="M 6 18 V 500"
                  fill="none"
                  stroke-width="2"
                  stroke="currentColor"
                ></path>
              </svg>
            </span>

            <div class="space-y-2">
              <p class="text-sm">
                {{ formatDate(startDate) }} - {{ formatDate(endDate) }}
              </p>

              <div class="flex space-x-2 text-xl">
                <h5 class="font-bold">{{ company }}</h5>
                <span>|</span>
                <h4 class="">{{ position }}</h4>
              </div>

              <ul class="list-disc">
                <li v-for="point in bulletPoints">
                  {{ point }}
                </li>
              </ul>

              <div>
                <p class="font-bold">Technologies:</p>
                <ul class="flex">
                  <li v-for="(tech, index) in technologies">
                    {{ tech }}
                    <span v-if="index < technologies.length - 1" class="mx-2"
                      >•</span
                    >
                  </li>
                </ul>
              </div>
            </div>
          </article>
        </li>
      </ul>
    </section>

    <section>
      <Heading>Projects</Heading>
      <Divider />

      <ul class="list-disc space-y-2">
        <li v-for="{ name, excerpt, website, github } in projects">
          <div class="flex space-x-2">
            <h3 class="text-lg font-bold">{{ name }}</h3>

            <template v-if="website">
              <span>|</span>
              <a :href="website" class="underline" target="_blank">
                <LinkIcon class="pr-1" />
                {{ website.replace("https://", "") }}</a
              >
            </template>

            <span>|</span>
            <a :href="github" class="underline" target="_blank">
              <GitHubIcon class="pr-1" />{{
                github?.replace("https://", "")
              }}</a
            >
          </div>
          <p class="text-sm">{{ excerpt }}</p>
        </li>
      </ul>
    </section>

    <section>
      <Heading>Certifications</Heading>
      <Divider />

      <ul class="space-y-1 list-disc">
        <li v-for="{ title, emitter, date, url } in certifications">
          <div class="flex space-x-2 items-center text-lg">
            <a :href="url" class="underline">
              <h5 class="font-bold">{{ title }}</h5>
            </a>
            <span>|</span>
            <h6>{{ emitter }}</h6>
          </div>
          <p class="text-sm">{{ formatDate(date) }}</p>
        </li>
      </ul>

      <a
        class="underline block pt-5"
        href="https://www.linkedin.com/in/diego-da-silva-8a06411a2/details/certifications/"
        target="_blank"
        >See all certifications ></a
      >
    </section>
  </main>
</template>
