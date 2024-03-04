<script lang='ts'>
  import NavBar from '../components/nav.svelte'
  import Content from '../components/header.content.svelte'
  import ArrowDown from '../components/arrow.down.svelte'
  export let data: any;
</script>

<header class='main_section'>
  <NavBar data={data.navBar} />
  <Content title={data.title} description={data.description} />
  <ArrowDown href='about'/>
</header>