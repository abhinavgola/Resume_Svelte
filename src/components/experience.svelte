

<script lang='ts'>
  import { fade } from 'svelte/transition';
  import Content from './experience.content.svelte';
  import ExperienceOption from './experience.option.svelte'

  const experiences: ExperienceItem[] = [
    {
      id: 0,
      role: 'Credit Risk Analyst Apprentice',
      business: 'Societe Generale',
      items: ['Developed the Referential Data System and worked with the RISQ team to build the IFRS9 PD model (RWA impact > €4 billion) for High-Net-Worth clients using decision tree classification', 'Conducted a data analysis of 450 data controls for 50 data points using SQL & VBA to build the Referential Data System for the IRBA LGD model for High-Net-Worth clients', 'Acted as the Data Quality Manager for the whole Private Banking division, updating past KQIs & implementing new ones in Power BI, presenting my feedback in quarterly meetings to data officers in UK, LUX, MON, FRA & SUI entities of SG Group'],
      date: 'October 2022 - Present'
    },
    {
      id: 1,
      role: 'Digital Project Management Intern',
      business: "L'Oreal",
      items: ["Collaborated with department leaders from IT, Business, Finance, Data and Customer Care to define, prioritize, and rollout L'Oréal’s Access 2.0 project in 104 countries","Identified all key tasks, dependencies, and milestones in each team for the Project delivery and worked on SAP integration and Business Process Mapping","Worked with the Finance and Business teams to allocate global, zone and local costs after conducting local gap analysis"],
      date: 'May 2022 - September 2022'
    },
    
    {
      id: 2,
      role: 'Project Manager Intern',
      business: 'Zakki',
      items: ['Coordinated a team of 6 members to develop a volunteer give-away platform for people in Jakarta, Indonesia','Conceived the definition of project scope and roadmap while monitoring the progress through dashboards','Acted as the “product owner” in the Agile team, preparing sprints while collaborating with the product team'],
      date: 'May 2021 - October 2021'
    },
    {
      id: 3,
      role: 'Product Planning Intern',
      business: 'LG Electronics India Pt. Ltd.',
      items: ['Collated and analysed data for 4 competitor organisations – Samsung, IFB, Panasonic and Bosch for the Home and Appliances department; Identified patterns and trends of the most profitable features of their key product: microwave ovens','Sensitivity analysis and business scenarios to identify and monitor key business drivers and risks'],
      date: 'August 2020 - September 2020'
    },
    {
      id: 4,
      role: 'Deep Learning Intern',
      business: 'Bennett University',
      items: ['Led a team of 6 for a face mask detection project focused on Indian society and implemented 3 detection pipelines (based on Python) on a self-created dataset of ~2000 images for real-time mask detection','Converted the YOLO v4 model to the TensorFlowRT model to increase efficiency up to 8 times and deployed it into an application'],
      date: 'June 2020 - July 2020'
    }
  ]
  let currentExperience: ExperienceItem = experiences[0];
  let selected: number = currentExperience.id;
  
  const handleClick = (value: ExperienceItem) => {
    if (currentExperience !== value)
      currentExperience = value
    selected = currentExperience.id
  }
</script>

<div class='flex items-center gap-8 flex-col justify-center w-full'>
 
  <div class='w-full px-6 lg:px-0 lg:w-2/5 gap-8 h-80 flex flex-col text-gray '>
    <div class='text-gray-light  rounded   text-xl lg:text-3xl flex items-end gap-2 lg:gap-4 text-center md:text-left lg:text-left  '>
      <span class='text-green-400  text-base lg:text-xl font-mono'> 03.</span> 
      <span class='text-left whitespace-nowrap font-bold'>Where I've worked</span>
      <div class='h-0.5 w-full bg-secondary mb-3.5 '></div>
    </div>
    <div class='flex flex-col lg:flex-row'>
      <div class='w-full overflow-x-auto scrollbar-thumb scrollbar-track scrollbar-thumb-red-200 scrollbar-track-red-600 lg:w-48 flex flex-row lg:flex-col '>
        {#each experiences as experience}
          <ExperienceOption selected={selected} handleClick={handleClick} experience={experience}/>
        {/each}
      </div>
      
      {#key currentExperience}
        <div in:fade class='pt-10 lg:pt-0 scrollbar-thin scrollbar-thumb scrollbar-track max-h-96 overflow-y-auto w-full  h-full '>
          <Content experience={currentExperience}/>
        </div>
      {/key}
    </div>

   
  </div>
</div>