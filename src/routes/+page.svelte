<script lang="ts">
    import { onMount } from 'svelte';
    import { Button } from "$lib/components/ui/button";
    import * as Card from "$lib/components/ui/card";
    import { goto } from "$app/navigation";
    import { Phone, Linkedin, Mail, Download, Eye } from "lucide-svelte";
    import Header from "$lib/components/header/header.svelte";
    import Experience from "$lib/components/experience/experience.svelte";
    import { Avatar } from '$lib/components/ui/avatar';

    onMount(() => {
        document.title = 'Home | Luis Chaparro';
    });

    const personalInfo = {
    name: "Luis Chaparro",
    location: "Venezuela",
    contact: "+58 412-5867955",
    email: "luis@chapi.dev",
    website: "https://www.chapi.dev",
    linkedin: "https://www.linkedin.com/in/chaparroluis",
  };

    const skills = [
      "Zoho CRM",
      "Zoho Recruit",
      "Zoho Forms",
      "Python",
      "Julia",
      "MySQL",
      "SQLite",
      "Svelte",
      "Google Colab",
      "Amazon Lightsail",
      "DigitalOcean",
      "Vultr",
      "Google Cloud",
      "Microsoft Azure",
    ];

    const education = [
      {
        institution: "Instituto Universitario Tecnológico Superior de Oriente",
        degree: "Higher Technician Diploma in the English Language",
        date: "December 2019",
      },
      {
        institution: "Colegio Salesiano Pio XII",
        degree: "High School Diploma in Data Processing",
        date: "August 2017",
      },
    ];

    const certifications = [
      {
        name: "DELF B2: French studies diploma level B2",
        issuer: "Minist\u00e8re de l'\u00c9ducation nationale et de la Jeunesse",
        date: "2019",
        id: "058281-201910T-4692535",
      },
      {
        name: "EF Standard English Test (EF SET) (C2 Proficient)",
        issuer: "EFSET English Certificate",
        date: "2023",
        score: "72/100 (C2 Proficient)",
        url: "https://www.efset.org/cert/T76Syx",
      },
      {
        name: "Advanced Conversational English",
        issuer: "Universidad Metropolitan",
        date: "2017",
      },
    ];


    function viewResume() {
        goto('/resume'); 
      }

    function downloadResume() {
        const link = document.createElement('a');
        link.href = '/Luis Chaparro CV EN.pdf';
        link.download = 'Luis Chaparro CV EN.pdf';
        link.click();
    }

</script>
  

<div class="min-h-screen flex flex-col font-sans">
  <Header />
  <main class="flex-grow p-4 md:p-10 grid md:grid-cols-2 gap-8">
      <div class="">
          <Card.Root id="about">
              <div class="md:flex md:gap-8">
                  <Card.Content class="md:w-full p-8 text-sm font-medium">
                      <div class="flex items-center gap-4">
                          <img src="lchaparro.png" alt="Luis Chaparro" class="rounded-full" />
                      </div>
                      <Card.Title class="whitespace-nowrap text-xl font-semibold tracking-tight border-b">Luis Chaparro</Card.Title>
                      <p class="text-base font-medium text-sm">IT Analyst</p>
                      <div class="leading-7 mt-6">
                          <p class="flex items center gap-2">
                              <Phone class="w-5 h-5" />
                              <span>{personalInfo.contact}</span>
                          </p>
                          <p class="flex items center gap-2">
                            <Linkedin class="w-5 h-5" />
                            <span><a href="{personalInfo.linkedin}" target="_blank" rel="noopener noreferrer">Luis Chaparro</a></span>
                          </p>
                          <p class="flex items center gap-2">
                            <Mail class="w-5 h-5" />
                            <span>{personalInfo.email}</span>
                          </p>
                      </div>
                      <div class="mt-10 flex gap-4">
                          <Button on:click={viewResume}>
                              <Eye class="w-5 h-5" />
                              <span class="p-2">Resume</span>
                          </Button>
                          <Button variant="outline" on:click={downloadResume}>
                              <Download class="w-5 h-5" />
                          </Button>
                      </div>
                  </Card.Content>
              </div>
          </Card.Root>

          <div class="mt-4 p-4 border-t">
            <div class="space-y-1">
              <h4 class="whitespace-nowrap text-xl font-semibold tracking-tight">About Me</h4>
              <p class="text-sm">
                From language lover to IT Analyst, a journey of passion and discovery. I always thought I would be a language teacher, or a translator. But as I delved deeper into the world of languages, I found myself drawn to the intricate 'languages' of Python and Julia, the 'grammar' of data analysis, and the 'syntax' of process automation. My switch from language teacher to coder felt natural and real. It was like learning a new dialect, one that spoke in Zoho, JavaScript, JQuery, HTML, Zapier, Tailwind, and Svelte. The thrill of implementing CRM and recruitment tools, developing software to import data from Google Drive to Zoho WorkDrive, and creating bots using Python was akin to mastering a challenging text in a foreign language. This journey has not only enriched my skills but also fueled my intrinsic motivation to learn more and make an impact.
              </p>
            </div>
          </div>

            <div id="skills" class="mt-4 p-4 border-t">
              <div class="space-y-1">
              <h4 class="whitespace-nowrap text-xl font-semibold tracking-tight">Skills</h4>
              <ul class="grid grid-cols-3 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-5 gap-4">
                {#each skills as skill}
                  <li>
                    <Button variant="outline">{skill}</Button>
                  </li>
                {/each}
              </ul>
            </div>
          </div>
      </div>

      <Experience />


  </main>

  <footer class="p-6 md:px-10">
    <div class="container mx-auto flex flex-col md:flex-row justify-between items-center">
      <div class="text-center md:text-left mb-4 md:mb-0 font-semibold text-sm">
        &copy; {new Date().getFullYear()} {personalInfo.name}
      </div>

      <div class="flex items-center space-x-4">
        <a href="mailto:{personalInfo.email}" target="_blank" rel="noopener noreferrer">
          <Mail class="w-5 h-5" />
        </a>
        <a href="{personalInfo.linkedin}" target="_blank" rel="noopener noreferrer">
          <Linkedin class="w-5 h-5" />
        </a>
        <a href="tel:{personalInfo.contact}">
          <Phone class="w-5 h-5" />
        </a>
      </div>
    </div>
  </footer>
</div>