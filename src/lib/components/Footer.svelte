<script>
  import Logo from "$lib/assets/fullLogoBlanco.png";
  import { faInstagram } from "@fortawesome/free-brands-svg-icons";
  import Fa from "svelte-fa";
</script>

<footer
  class="footer flex justify-between items-center p-4 md:px-10 mb-16 lg:mb-0 bg-neutral text-neutral-content"
>
  <div class="items-center grid-flow-col">
    <img class="w-24 lg:w-36" src={Logo} alt="XCargo Logo" />
    <p class="text-xs">
      Copyright © XCargo Services 2023 - Derechos Reservados
    </p>
  </div>
  <div class="grid-flow-col gap-4 md:place-self-center md:justify-self-end">
    <a href="https://www.instagram.com/xcargoservicespty507"
      ><Fa icon={faInstagram} class="text-3xl" /></a
    >
  </div>
</footer>
