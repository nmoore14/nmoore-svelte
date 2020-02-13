<script>
  import Hamburguer from "./Hamburguer.svelte";
  import NavLink from "./NavLink.svelte";

  export let segment;
  let expand = false;

  function toggleMobileMenu(event) {
    expand = event.detail;
  }
</script>

<nav
  class="z-10 fixed flex flex-row p-2 bg-transparent justify-between"
>

  <a href="." class="font-semibold text-xl tracking-tight mr-4">
    Your project name
  </a>

  <div class="block lg:hidden">
    <Hamburguer on:click={toggleMobileMenu} {expand} />
  </div>
  <div class="w-full block flex-grow lg:flex lg:items-center lg:w-auto">
    <div class="{!expand && 'hidden'} lg:block text-sm lg:flex-grow">
      <NavLink text="About" href="about" {segment} />
      <NavLink text="Blog" href="blog" {segment} rel="prefetch" />
    </div>
  </div>
</nav>
