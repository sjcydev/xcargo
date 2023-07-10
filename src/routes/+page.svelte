<script>
  import AbrirCasillero from "$lib/components/AbrirCasillero.svelte";
  import { blur } from "svelte/transition";
  import { onMount } from "svelte";

  import Fa from "svelte-fa";
  import {
    faBoxesPacking,
    faClock,
    faMapLocationDot,
    faPhone,
    faPlaneDeparture,
    faShip,
    faWarehouse,
  } from "@fortawesome/free-solid-svg-icons";
  import { goto } from "$app/navigation";

  let precio = "$2.50";

  let servicios = [
    {
      titulo: "Carga Aérea",
      contenido:
        "Servicio de transporte rápido y seguro de mercancías por avión, ideal para tus compras en linea",
      icono: faPlaneDeparture,
    },
    {
      titulo: "Carga Marítima",
      contenido:
        "Solución económica y confiable para el transporte de grandes volúmenes de mercancías por barco a nivel internacional",
      icono: faShip,
    },
    {
      titulo: "Deposíto en Miami",
      contenido:
        "Nuestro depósito estratégicamente ubicado en Miami ofrece almacenamiento seguro y servicios de distribución eficientes para tus pedidos.",
      icono: faWarehouse,
    },
  ];

  let direccionMapa = "https://maps.app.goo.gl/6umy2Deq1bqTzmZT6?g_st=ic";

  let ready = false;
  onMount(() => (ready = true));
</script>

<svelte:head>
  <title
    >XCargo Services - Agencia de Carga Internacional con Base en Miami y Panama</title
  >
</svelte:head>

<div
  class="hero min-h-screen relative justify-items-start"
  style="background-image:
  url(https://images.unsplash.com/photo-1645526816847-74a7640b8b7d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80)"
>
  <div class="hero-overlay bg-opacity-30" />
  {#if ready}
    <div
      in:blur={{ duration: 750, amount: 2 }}
      class="hero-content text-secondary-content flex-col
    lg:flex-row my-20 md:px-20 min-[1235px]:px-36 lg:my-0 max-w-full w-full justify-between"
    >
      <div class="text-left p-4 lg:p-0">
        <h1
          class="titulo mb-5 text-4xl min-[1024px]:text-6xl min-[1235px]:text-8xl font-semibold"
        >
          Delivery <span class="block">Rápido & Seguro</span>
        </h1>
        <p class="mb-5 min-[1235px]:text-lg">
          Te facilitamos tus compras por internet. Recibe todas tus compras del
          cualquier parte del mundo.
        </p>
        <button
          class="btn btn-secondary hidden min-[1235px]:block max-[1024px]:w-full"
          on:click={() => goto("/registrar")}>Abre tu Casillero Gratis</button
        >
      </div>
      <div class="">
        <AbrirCasillero />
      </div>
    </div>
  {/if}
</div>

<div class="grid place-items-center p-8">
  <h1 class="text-center text-2xl lg:text-3xl font-semibold max-w-xl my-12">
    Te aseguramos un rápido y seguro transporte para tus paquetes
  </h1>
  <div class="grid md:grid-cols-3 gap-8 md:gap-4 lg:gap-10">
    {#each servicios as servicio}
      <div
        class="card bg-base-200
      shadow-lg rounded-none max-w-sm"
      >
        <div class="p-7 md:p-8 lg:px-8 lg:pt-10 justify-start">
          <Fa class="text-2xl text-secondary" icon={servicio.icono} />
        </div>
        <div class="card-body p-7 pt-0 md:p-8 md:pt-0 font-light">
          <h2 class="card-title text-base lg:text-lg">{servicio.titulo}</h2>
          <p class="text-sm lg:text-base">{servicio.contenido}</p>
        </div>
      </div>
    {/each}
  </div>
</div>

<div class="hero bg-base-100">
  <div
    class="hero-content grid md:grid-cols-2 md:my-16 lg:my-24 px-6 place-items-center"
  >
    <img
      src="https://images.unsplash.com/photo-1620455800201-7f00aeef12ed?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=687&q=80"
      class="max-w-md w-full shadow-xl"
      alt="Bus con paquetes"
    />
    <div class="mb-10 mt-6">
      <h1 class="text-3xl font-bold max-w-lg">
        Solución Confiable para Compras en Internet
      </h1>
      <div class="max-w-lg">
        <p class="py-6 text-justify">
          Ofrecemos una solución integral y confiable para tus necesidades de
          compras por internet.
        </p>
        <p class="pb-6 text-justify">
          Nuestro equipo experto se encarga de gestionar eficientemente tus
          envíos, brindando un servicio confiable y seguro en cada etapa del
          proceso.
        </p>
        <p class="mb-12 text-justify">
          Confía en nosotros para una compra fluida y un transporte confiable de
          tus pedidos.
        </p>
      </div>
      <button class="btn btn-secondary" on:click={() => goto("/registrar")}
        >Abre tu casillero</button
      >
    </div>
  </div>
</div>

<div
  class="hero h-[27em] relative"
  style="background-image:
    url(https://images.unsplash.com/photo-1566576721346-d4a3b4eaeb55?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=765&q=80);"
>
  <div class="hero-overlay bg-opacity-30" />
  <div class="hero-content text-center text-secondary-content">
    <div class="max-w-md">
      <h1 class="mb-5 text-4xl lg:text-5xl font-bold">Una vez en Miami</h1>
      <p class="mb-5">Le entregamos su paquete en 48 horas!</p>
      <button class="btn btn-secondary" on:click={() => goto("/registrar")}
        >Comprar en Linea Ahora</button
      >
    </div>
  </div>
</div>

<div
  class="card text-neutral-focus grid place-items-center px-10 lg:px-20 my-10"
>
  <div class="lg:px-36 grid lg:grid-cols-2 w-full lg:w-3/4 place-items-center">
    <div>
      <div class="mb-10 grid place-items-center">
        <h2 class="text-2xl lg:text-4xl my-10">Tarifa Unica</h2>
        <Fa class="text-7xl lg:text-9xl" icon={faBoxesPacking} />
        <div class="my-10 text-center">
          <p class="text-2xl lg:text-3xl mb-3">
            {precio}
            <span class="text-lg"
              ><span class="text-xl lg:text-2xl">/</span> libra sin volumen</span
            >
          </p>
          <p class="text-base">Tarifa a nivel nacional</p>
        </div>
      </div>
    </div>
    <div>
      <p class="text-xl lg:text-2xl mb-5">
        Todo es mas <span class="font-medium">FACIL</span> con nosotros!
      </p>
      <p class="text-base lg:text-xl font-extralight mb-12">
        Solo te facturamos lo que traes. Con una sola tarifa no te tienes que
        preocupar de nada mas. Consigue tu casillero <span class="font-normal"
          >GRATIS</span
        >!
      </p>
      <div class="text-right">
        <button
          class="btn btn-secondary max-[1024px]:w-full"
          on:click={() => goto("/registrar")}>Consigue tu Casillero</button
        >
      </div>
    </div>
  </div>
</div>

<div
  class="hero lg:h-[30em] relative"
  style="background-image:
    url(https://images.unsplash.com/photo-1633174524827-db00a6b7bc74?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1496&q=80);"
>
  <div class="hero-overlay bg-opacity-40" />
  <div class="hero-content text-center text-secondary-content py-20 px-14">
    <div class="max-w-md">
      <h1 class="mb-5 text-3xl lg:text-5xl font-medium">
        Abre tu cuenta totalmente
        <span class="font-bold">GRATIS</span>!
      </h1>
      <p class="mb-5">
        Te traemos todas tus compras de cualquier parte del mundo a Panamá! Abre
        tu casilla hoy, es GRATIS Ofrecemos también el servicio a domicilio, el
        costo depende del área de entrega.
      </p>
      <button class="btn btn-secondary" on:click={() => goto("/registrar")}
        >Abre tu Cuenta Gratis</button
      >
    </div>
  </div>
</div>

<div class="hero lg:h-fit relative bg-base-100">
  <div class="hero-content text-netural-focus justify-stretch w-full md:p-8">
    <div class="grid md:grid-cols-2 lg:place-content-center lg:align-top">
      <div class="w-full p-5 md:pl-10">
        <h1
          class="mb-3 text-2xl lg:text-3xl font-medium flex items-center gap-2"
        >
          <Fa icon={faClock} /> Horario
        </h1>
        <div>
          <div class="mb-2">
            <p class="text-lg font-medium">Lunes - Sabado</p>
            <p>8:00 AM - 6:00 PM</p>
          </div>
          <p class="text-lg font-medium">Domingo</p>
          <p>8:00 AM - 12:00 PM</p>
        </div>
      </div>
      <div class="p-5 mb-10">
        <h2 class="text-2xl lg:text-3xl font-medium mb-1">xCargo Services</h2>
        <div class="grid lg:grid-cols-2 lg:gap-10 mb-3">
          <div>
            <a
              href="https://wa.me/+50766302373"
              class="text-lg mb-2 flex place-items-center gap-2"
              target="_blank"
            >
              <Fa icon={faPhone} /> +507 6362-8879
            </a>
          </div>
        </div>
        <p class="mb-1 text-base">La Chorrera</p>
        <p class="mb-6 text-sm">
          Barrio Balboa, Ave Ricardo J. Alfaro (Calle Rockefeller), Pb
          Autoservicio Mario
        </p>
        <button
          class="btn btn-neutral"
          on:click={() => window.open(direccionMapa, "_blank")}
          ><Fa icon={faMapLocationDot} /> Direccion</button
        >
      </div>
    </div>
  </div>
</div>
