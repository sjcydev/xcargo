<script>
  import { goto } from "$app/navigation";
  import { page } from "$app/stores";
  import Logo from "$lib/assets/fullLogoBlanco.png";
  import Fa from "svelte-fa";
  import { faTruckPlane, faBoxOpen } from "@fortawesome/free-solid-svg-icons";
</script>

<nav
  class="hidden z-[-1] lg:z-50 navbar w-full bg-transparent lg:flex
  justify-between md:px-20 min-[1235px]:px-36 py-5 lg:text-base absolute top-0"
>
  <a href="/">
    <img src={Logo} class="w-36" alt="DropCargo Express Logo" />
  </a>
  <ul
    class="menu menu-vertical lg:menu-horizontal lg:text-base
    text-secondary-content"
  >
    <li><a class="hover:bg-white hover:text-black" href="/">Inicio</a></li>
    <li>
      <a class="hover:bg-white hover:text-black" href="/tracking">Tracking</a>
    </li>
    <li>
      <a class="hover:bg-white hover:text-black" href="/registrar"
        >Abrir Cuenta</a
      >
    </li>
  </ul>
</nav>

<nav
  class="lg:hidden navbar px-10 py-5 bg-transparent {$page.url.pathname ===
  '/registrar'
    ? 'fixed'
    : 'absolute'} top-0 z-[50]"
>
  <a href="/">
    <img src={Logo} class="w-32" alt="DropCargo Express Logo" />
  </a>
</nav>
<nav class="fixed bottom-0 z-50 navbar lg:hidden">
  <div class="btm-nav">
    <button
      class={$page.url.pathname === "/" ? "active" : ""}
      on:click={() => goto("/")}
    >
      <svg
        xmlns="http://www.w3.org/2000/svg"
        class="h-5 w-5"
        fill="none"
        viewBox="0 0 24 24"
        stroke="currentColor"
        ><path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6"
        /></svg
      >
    </button>
    <button
      class={$page.url.pathname === "/tracking" ? "active" : ""}
      on:click={() => goto("/tracking")}
    >
      <Fa class="h-5 w-5" icon={faTruckPlane} />
    </button>
    <button
      class={$page.url.pathname === "/registrar" ? "active" : ""}
      on:click={() => goto("/registrar")}
    >
      <Fa class="h-5 w-5" icon={faBoxOpen} />
    </button>
  </div>
</nav>
