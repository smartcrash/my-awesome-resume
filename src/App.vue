<script setup lang="ts">
import { format } from "date-fns";
import { chunk, orderBy } from "lodash";
import Divider from "./components/Divider.vue";
import EnvelopeIcon from "./components/EnvelopeIcon.vue";
import GitHubIcon from "./components/GitHubIcon.vue";
import Heading from "./components/Heading.vue";
import LinkIcon from "./components/LinkIcon.vue";
import LinkedinIcon from "./components/LinkedinIcon.vue";

const formatDate = (date: Date) => format(date, "LLL y");

const skills: string[] = [
  "Node.js",
  "TypeScript",
  "React",
  "AWS",
  "DepOps",
  "CI/CD",
  "Docker",
  "PostgreSQL",
];

const experiece: {
  company: string;
  startDate: Date;
  endDate: Date | null;
  position: string;
  bulletPoints: string[];
  technologies: string[];
}[] = [
    {
      company: "Bizcuit B.V",
      position: "Medior Software Developer",
      startDate: new Date(2022, 9, 0),
      endDate: null,
      bulletPoints: [
         "Enhanced a Node.js application by maintaining existing functionalities and implementing new features, while leveraging my <strong>Node.js</strong> and <strong>AWS</strong> knowledge to enhance code quality and infrastructure.",
        "Successfully reduced the high GPU utilisation of the Production RDS instance from <strong>98%</strong> to a remarkable <strong>3%</strong>, enabling substantial downscaling and yielding significant savings in RDS-related expenses.",
        "Enhanced the observability of the production application, facilitating quicker error detection and the identification of performance bottlenecks.",
        "Demonstrated agility in resolving critical incidents promptly to ensure minimal downtime for users."
      ],
      technologies: [],
    },

    {
      company: "Cliengo",
      position: "Back-End Developer",
      startDate: new Date(2021, 8, 0),
      endDate: new Date(2022, 3, 0),
      bulletPoints: [
        "Spearheaded the development of custom features for an advanced Chatbot, tailoring solutions to diverse client requirements",
        "Leveraged expertise in <strong>Node.js</strong> and <strong>AWS Lambdas</strong> to optimize Chatbot performance, resulting in a significant enhancement in overall user experience and client satisfaction."
      ],
      technologies: ["Node.js", "AWS Lambdas", "API Gateway"],
    },

    {
      company: "Ordde S.A",
      position: "Full-stack Web Developer",
      startDate: new Date(2021, 1, 0),
      endDate: new Date(2021, 8, 0),
      bulletPoints: [
        "Played a pivotal role in the development of a substantial application, collaborating closely with a talented team, and gaining valuable insights into effective teamwork dynamics.",
        "Demonstrated a remarkable ability to swiftly assimilate the team's workflow and proficiently navigate their tech stack, including <strong>Node.js</strong>, <strong>JavaScript</strong>, <strong>Meteor JS</strong>, <strong>MongoDB</strong>, enabling me to contribute to new feature implementation within a mere couple of weeks.",
      ],
      technologies: ["JavaScript", "Meteor JS", "MongoDB", "CircleCI"],
    },

    {
      company: "Workana",
      position: "Freelancer",
      startDate: new Date(2020, 3, 0),
      endDate: new Date(2021, 1, 0),
      bulletPoints: [
        "Consistently achieved outstanding client satisfaction by successfully delivering a diverse range of projects, all centered around <strong>JavaScript</strong>, <strong>Node.js</strong> and/or <strong>PHP</strong> technologies.",
        "As a proactive freelancer, honed exceptional communication and adaptability skills, proving instrumental in navigating the demands of this dynamic industry.",
        "Proficiently utilized a wide array of technologies, including <strong>Node.js</strong>, <strong>JavaScript</strong>, <strong>React</strong>, <strong>Vue</strong>, <strong>PHP</strong>, <strong>Laravel</strong>, and databases like <strong>MySQL</strong> and <strong>PostgreSQL</strong>, to develop innovative solutions that exceed client expectations."
      ],
      technologies: [
        "JavaScript",
        "React",
        "Vue",
        "PHP",
        "Laravel",
        "MySQL",
        "PostgreSQL",
      ],
    },

    {
      company: "System Click s.a",
      position: "Junior Software Developer ",
      startDate: new Date(2017, 10, 0),
      endDate: new Date(2019, 12, 0),
      bulletPoints: [
        "Collaborated on the successful development of diverse products, ranging from Administrative Software and Desktop Applications to CMS and Web Sites, contributing to the acquisition of a robust skill set in the field.",
        "Proficiently employed a variety of technologies, including <strong>Node.js</strong>, <strong>JavaScript</strong>, <strong>React</strong>, <strong>Vue</strong>, <strong>Electron</strong> for desktop applications, and database management systems like <strong>MongoDB</strong> and <strong>PostgreSQL</strong>, to deliver high-quality solutions that met client requirements and industry standards."
      ],
      technologies: ["JavaScript", "React", "Vue", "Electron", "MongoDB", "PostgreSQL"],
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
    title:
      "Divide and Conquer, Sorting and Searching, and Randomized Algorithms",
    emitter: "Coursera",
    date: new Date(2021, 11, 0),
    url: "https://www.coursera.org/account/accomplishments/verify/9C9T4CXA4DXK",
  },

  {
    title: "Natural Language Processing with Classification and Vector Spaces",
    emitter: "Coursera",
    date: new Date(2021, 10, 0),
    url: "https://www.coursera.org/account/accomplishments/certificate/452UQT3FUFGM",
  },
]

const projects: {
  name: string;
  excerpt: string;
  website?: string;
  github: string;
  technologies: string[];
}[] = [
    {
      name: "Liboards",
      excerpt: "An Issue Tracker to organize your projects",
      website: "https://liboards.space",
      github: "https://github.com/smartcrash/liboards",
      technologies: [
        "React",
        "Express",
        "GraphQL",
        "TypeScript",
        "Heroku",
        "Vercel",
        "Vitest",
        "Jest",
        "Cypress",
      ],
    },

    {
      name: "Another TODO List",
      excerpt: "A simple and beautiful TODO list app",
      github: "https://github.com/smartcrash/another-todo-list",
      technologies: [
        "React",
        "Express",
        "GraphQL",
        "TypeScript",
        "Vitest",
        "Jest",
        "Cypress",
      ],
    },
  ];
</script>

<template>
  <main class="mx-auto text-gray-700 space-y-5 px-10 pt-8" :style="{ maxWidth: '1200px' }">
    <section class="text-center relative">
      <h1 class="text-4xl font-black">
        Diego Da'Silva
      </h1>

      <h2 class="text-xl italic mb-5">
        Software Engineer
      </h2>
      <h5 class="space-x-3 mt-2">
        <span><a href="mailto:smartcrashomg@gmail.com" class="underline">
            <EnvelopeIcon />
            smartcrashomg@gmail.com
          </a>
        </span>
        <span>|</span>
        <a href="tel:+310622575275">+31 06 2257 52 75</a>
        <span>|</span>
        <span>
          <a href="https://linkedin.com/in/diego-da-silva-developer" class="underline" target="_blank">
            <LinkedinIcon class="pr-1" />
            linkedin.com/in/diego-da-silva-developer
          </a>
        </span>
      </h5>
    </section>

    <section>
      <Heading>Technical Skills</Heading>

      <Divider />

      <dl class="grid grid-cols-3 pl-4 gap-1 text-base">
        <template v-for="(chunks, index) in chunk(skills, 3)">
          <ul class="list-disc">
            <li v-for="(skill, index) in chunks">
              {{ skill }}
            </li>
          </ul>
        </template>
      </dl>
    </section>

    <section>
      <Heading>Professional Experience</Heading>

      <Divider />

      <ul class="space-y-3 overflow-hidden">
        <li v-for="{
          company,
          position,
          startDate,
          endDate,
          bulletPoints,
          technologies,
        } in experiece">
          <article class="relative pl-10">
            <span class="flex col-span-2 items-center absolute top-1 left-0">
              <svg viewBox="0 0 12 12" class="w-3 h-3 mr-6 overflow-visible">
                <circle cx="6" cy="6" r="6" fill="currentColor"></circle>
                <path d="M 6 18 V 500" fill="none" stroke-width="2" stroke="currentColor"></path>
              </svg>
            </span>

            <div class="space-y-2">
              <div>
                <h5 class="font-bold text-lg">{{ company }}</h5>
                <div class="flex items-center space-x-2">
                  <h4 class="italic">{{ position }}</h4>
                  <span>|</span>
                  <p class="text-sm">
                    {{ formatDate(startDate) }} - {{ endDate ? formatDate(endDate) : 'Present' }}
                  </p>
                </div>
              </div>

              <ul class="list-disc pl-3 text-sm">
                <li v-for="point in bulletPoints" v-html="point">
                </li>
              </ul>

              <div class="hidden">
                <p class="font-bold">Technologies:</p>
                <ul class="flex">
                  <li v-for="(tech, index) in technologies">
                    {{ tech }}
                    <span v-if="index < technologies.length - 1" class="mx-2">•</span>
                  </li>
                </ul>
              </div>
            </div>
          </article>
        </li>
      </ul>
    </section>

    <section class="hidden">
      <Heading>Projects</Heading>
      <Divider />

      <ul class="grid grid-cols-2 grid-flow-col list-disc gap-16">
        <li v-for="{ name, excerpt, website, github, technologies } in projects">
          <div class="flex space-x-2">
            <h3 class="text-lg font-bold">{{ name }}</h3>

            <template v-if="website">
              <span>|</span>
              <a :href="website" class="underline" target="_blank">
                <LinkIcon class="pr-1" />
                {{ website.replace("https://", "") }}
              </a>
            </template>

            <span>|</span>
            <a :href="github" class="underline" target="_blank">
              <GitHubIcon class="pr-1" />{{
                github?.replace("https://", "")
              }}
            </a>
          </div>
          <p class="text-sm">{{ excerpt }}</p>

          <p class="font-bold mt-2 mb-1">Technologies:</p>
          <ul class="flex flex-wrap space-x-1 text-sm">
            <li v-for="(technologie, index) in technologies" class="flex items-center">
              {{ technologie }}
              <span v-if="index < technologies.length - 1" class="mx-2">•</span>
            </li>
          </ul>
        </li>
      </ul>
    </section>

    <section class="relative">
      <Heading>Certifications</Heading>
      <Divider />

      <ul class="space-y-1 list-disc pl-4">
        <li v-for="{ title, emitter, date, url } in certifications">
          <div class="flex justify-between space-x-2 items-center">
            <a :href="url" class="underline">
              <h5 class="font-bold">{{ title }}</h5>
            </a>
            <p class="text-sm">{{ formatDate(date) }}</p>
          </div>
        </li>
      </ul>

      <a class="underline block absolute top-1 right-0"
        href="https://www.linkedin.com/in/diego-da-silva-8a06411a2/details/certifications/" target="_blank">See all
        certifications ></a>
    </section>
  </main>
</template>
