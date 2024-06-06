<script lang="ts">
    import * as Card from "$lib/components/ui/card";
    import { ScrollArea } from "$lib/components/ui/scroll-area";
    import { Badge } from "$lib/components/ui/badge";
    
    const experience = [
    {
      company: "Sell2Rent",
      title: "Zoho Developer",
      location: "Remote",
      dates: "September 2023 - Present",
      responsibilities: [
        "Administration of Zoho CRM and Recruit, including implementation of new features, troubleshooting, and updates.",
        "Development of a comprehensive revenue breakdown tool, incorporating lead generation partners, lead/deal teams, and expenses.",
        "Creation of a 'deals days counter' to track the duration of deals in different stages.",
        "Implementation of a date-based counter and proficiency in schedule management, command center utilization, and integration with lead generation partners using Zapier and Zoho Flow.",
      ],
    },
    {
      company: "IP Immigration Pros Inc.",
      title: "IT Analyst",
      location: "Remote",
      dates: "November 2021 - September 2023",
      responsibilities: [
        "Created, reviewed, and managed company reports using Julia and Python for data analysis and workload distribution. Libraries used in Julia were DataFrames.jl, CSV.jl and Dates.jl.",
        "Provided technical support to employees on operating systems (Linux, macOS, Windows) and software issues.",
        "Assisted in document preparation in Spanish, English, and French.",
        "Implemented Zoho CRM, Recruit, Books, and Projects using Zoho Flow, Zapier, Python, Zoho Workflows, and Zoho Blueprints.",
        "Wrote code in Python, Julia and Zoho Deluge. Read code in the R Language for analysis of previous workloads.",
        "Created library in Julia to improve the import of data from Streak (CRM Software for Gmail) using their API (https://github.com/chapig/streak). This wrapper was later used to create a workload distribution report for the case processing team who are responsible for submitting clients\u2019 immigration dossiers.",
      ],
    },
    {
      company: "Philon Group",
      title: "Python Developer",
      location: "Lecher\u00eda, Venezuela",
      dates: "January 2022 - September 2023",
      responsibilities: [
        "Contributed to the largest Latin American NFT project, The Nifty Way Galaxy, generating over $1M USD in sales.",
        "Developed and deployed multiple Discord bots using the Python Wrapper API (py-cord and discord.py) for enhanced user engagement.",
        "Managed client referrals through SQLite and implemented an in-game currency system for events and minigames like escape rooms and slot machines.",
        "Ensured in-game currency could not be purchased or transferred to maintain a fair reward system.",
      ],
    },
    {
      company: "Self Employed",
      location: "Remote",
      title: "Python Developer and IT Analyst",
      dates: "2019 - 2022",
      responsibilities: [
        "Created several bots to be used on Discord for personal and several clients that requested:",
        "\u2002 Manage invitations, store them in a SQLite database and access a view of it through Google Sheets.",
        "\u2002 Used services from Amazon Web Services (AWS), Microsoft Azure and Google Cloud, such as Sentiment Analysis, Text to Speech, Translator, and MySQL databases.",
        "Deployed succesfully several applications using DigitalOcean, Microsoft Azure, Google Cloud, Vercel, Amazon Web Services, Amazon Lightsail, and Vultr.",
        "Developed a personal blog where articles written by me were posted. Website was built using Svelte, TailwindCSS, FastAPI and was deployed using Amazon Lightsail and Vercel.",
        "Created and deployed personal website https://www.chapi.dev",
      ],
    },
  ];
</script>

<style>
  /* Style the scrollbar (customize as you like) */
  .custom-scrollbar::-webkit-scrollbar {
    width: 8px;
  }

  .custom-scrollbar::-webkit-scrollbar-track {
    background: #f1f1f1;
  }

  .custom-scrollbar::-webkit-scrollbar-thumb {
    background: #888;
    border-radius: 4px;
  }

  .custom-scrollbar::-webkit-scrollbar-thumb:hover {
    background: #555;
  }
</style>

<Card.Root id="experience" class="max-w-2xl rounded-lg shadow-md overflow-hidden md:mx-auto" aria-label="Work History">
  <Card.Header>
    <Card.Title class="scroll-m-20 border-b pb-2 text-3xl whitespace-nowrap text-xl font-semibold tracking-tight text-gray-900 dark:text-white"> 
      Work History
    </Card.Title>
  </Card.Header>

  <Card.Content class="overflow-hidden">
    <ScrollArea class="h-screen focus:outline-none" tabindex={0}>
      <div class="overflow-y-auto custom-scrollbar" role="list" aria-label="Job Experiences">
        {#each experience as item (item.company)}
          <div class="mb-6 leading-7 border-b pb-4" role="listitem">
            <h3 class="scroll-m-20 text-2xl font-semibold tracking-tight text-gray-900 dark:text-white" aria-label="Job Title">{item.title} at {item.company}</h3>
            <p class="mt-2 text-base font-medium text-gray-700 dark:text-gray-300" aria-label="Location and Dates">
              <Badge>{item.location}</Badge> | {item.dates}
            </p>
            <ul class="list-disc list-inside [&>li]:mt-1 font-normal text-sm text-gray-700 dark:text-gray-300" aria-label="Responsibilities">
              {#each item.responsibilities as responsibility}
                <li>{responsibility}</li>
              {/each}
            </ul>
          </div>
        {/each}
      </div>
    </ScrollArea>
  </Card.Content>
</Card.Root>