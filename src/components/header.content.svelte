
<script lang='ts'>
    export let title: string;
    export let description: string;
  </script>
  <div class=' flex flex-col items-center h-full'>
    <div class=' w-full md:w-2/3 lg:w-2/3  flex items-start justify-start text-left  px-10 absolute top-1/2  transform  -translate-y-1/2 fadeIn '>
      <div class='flex flex-col gap-4 '>
        <p class="text-green-400 font-mono pl-1">Hi, my name is</p>
        <h1 class=' text-gray-light font-black text-4xl  md:text-5xl lg:text-7xl'>
          {title}.
        </h1>
        <div>
          <p class=' text-md lg:text-xl text-gray w-full lg:w-2/3'>
            {description}
          </p> 
          <h2 class= 'pt-14 text-4xl md:text-5xl lg:text-6xl text-gray font-bold'>Welocme to my website.</h2>
 
        </div>

      </div>	
    </div>
  </div>