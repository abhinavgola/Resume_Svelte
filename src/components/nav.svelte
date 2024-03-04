<script lang='ts'>
  import NavItem from '../components/nav.item.svelte'
  export let data: any;
  import { onMount } from 'svelte'
    let currentScroll = 0
    let show = false
    onMount(() => {
      window.onscroll = () => {
        if (window.scrollY > currentScroll) {
          show = true
          currentScroll = window.scrollY
        } else {
          show = false
          currentScroll = window.scrollY - 1
        }
      }
    })
</script>

<nav class:scrolled={show} class="font-mono z-20 glass scrolled fixed w-full  py-6 flex select-none  shadow-2xl ">
  <div class='h-12 flex text-gray mx-8 text-center justify-center items-center'>
    <img src="/images/logo_AG.png" alt="logo" class='h-full'>
  </div>
  <div class='hidden mr-10 gap-8 w-full md:flex justify-end items-center ' id='nav' >
    {#each data as item, index}
      <NavItem href ='../components/{item}.svelte' itemName={item} index={index}/>
	  {/each}
  </div>
</nav>
