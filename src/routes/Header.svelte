<script lang="ts">
  import { page } from "$app/stores";
 

  import { fade, fly } from 'svelte/transition';
  let showMobile: boolean = false;
  function openMobileMenu() {
    showMobile = true;
  }
  function closeMobileMenu() {
    showMobile = false;
  }
  export let visible = false;

</script>

<!-- <div class="corner">
		<a href="https://kit.svelte.dev">
			<img src={logo} alt="SvelteKit" />
		</a>
	</div>

	<nav>
		<svg viewBox="0 0 2 3" aria-hidden="true">
			<path d="M0,0 L1,2 C1.5,3 1.5,3 2,3 L2,0 Z" />
		</svg>
		<ul>
			<li aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
				<a href="/">Home</a>
			</li>
			<li aria-current={$page.url.pathname === '/about' ? 'page' : undefined}>
				<a href="/about">About</a>
			</li>
			<li aria-current={$page.url.pathname.startsWith('/sverdle') ? 'page' : undefined}>
				<a href="/sverdle">Sverdle</a>
			</li>
		</ul>
		<svg viewBox="0 0 2 3" aria-hidden="true">
			<path d="M0,0 L0,3 C0.5,3 0.5,3 1,2 L2,0 Z" />
		</svg>
	</nav>

	<div class="corner">
		<a href="https://github.com/sveltejs/kit">
			<img src={github} alt="GitHub" />
		</a>
	</div> -->
<!-- <header class="relative bg-none text-white rounded-lg">
  <nav
    class="mx-auto flex max-w-7xl items-center justify-between p-6 lg:px-8"
    aria-label="Global"
  >
    <div class="flex lg:flex-1">
      <a href="/" class="-m-1.5 p-1.5">
        <span class="text-white sr-only">Your Company</span>
        <h1 class="text-white text-2xl font-bold">Your Company</h1>
      </a>
    </div>
    <div class="flex lg:hidden text-white">
      <button
        on:click={openMobileMenu}
        type="button"
        class="-m-2.5 inline-flex items-center justify-center rounded-md p-2.5 text-white"
      >
        <span class="sr-only">Open main menu</span>
        <svg
          class="h-6 w-6 text-white"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
          aria-hidden="true"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"
          />
        </svg>
      </button>
    </div>
    <div class="hidden lg:flex lg:gap-x-12">
      <a href="#sell" class="text-sm font-semibold leading-6 text-white">Sell</a
      >
      <a href="#pitches" class="text-sm font-semibold leading-6 text-white"
        >Pitches</a
      >
      <a
        href="#contributions"
        class="text-sm font-semibold leading-6 text-white">About</a
      >
      <a href="#contacts" class="text-sm font-semibold leading-6 text-white"
        >Company</a
      >
    </div>
    <div class="hidden lg:flex lg:flex-1 lg:justify-end">
      <a href="/login" class="text-sm font-semibold leading-6 text-white"
        >Log in <span aria-hidden="true">&rarr;</span></a
      >
    </div>
  </nav>
 
  {#if showMobile}
    <div
      class="lg:hidden bg-gradient-to-r from-[#1D267D] via-gray-[#0C134F] to-[#1D267D] text-white"
      role="dialog"
      aria-modal="true"
    >
      
      <div class="fixed inset-0 z-10" />
      <div
        class="fixed inset-y-0 right-0 z-10 w-full overflow-y-auto bg-gradient-to-r from-[#1D267D] via-gray-[#0C134F] to-[#1D267D] text-white px-6 py-6 sm:max-w-sm sm:ring-1 sm:ring-gray-900/10"
      >
        <div class="flex items-center justify-between">
          <a href="login" class="-m-1.5 p-1.5">
            <span class="sr-only text-white">Your Company</span>
            <img
              class="h-8 w-auto"
              src="https://tailwindui.com/img/logos/mark.svg?color=indigo&shade=600"
              alt=""
            />
          </a>
          <button
            on:click={closeMobileMenu}
            type="button"
            class="-m-2.5 rounded-md p-2.5 text-gray-700"
          >
            <span class="sr-only">Close menu</span>
            <svg
              class="h-6 w-6 text-white"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              aria-hidden="true"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </button>
        </div>
        <div class="mt-6 flow-root">
          <div class="-my-6 divide-y divide-gray-500/10">
            <div class="space-y-2 py-6">
              <a
                href="#sell"
                class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-white hover:bg-blue-500"
                >Sell</a
              >
              <a
                href="#pitches"
                class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-white hover:bg-blue-500"
                >Features</a
              >
              <a
                href="#contributions"
                class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-white hover:bg-blue-500"
                >Marketplace</a
              >
              <a
                href="#contacts"
                class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-white hover:bg-blue-500"
                >Company</a
              >
            </div>
            <div class="py-6">
              <a
                href="/login"
                class="-mx-3 block rounded-lg px-3 py-2.5 text-base font-semibold leading-7 text-white hover:bg-blue-800"
                >Log in</a
              >
            </div>
          </div>
        </div>
      </div>
    </div>
  {/if}
</header> -->
<header class="">
	<nav class="mx-auto flex max-w-7xl items-center justify-between gap-x-6 p-6 lg:px-8" aria-label="Global">
		<div class="flex lg:flex-2">
		  <div  class="-m-1.5 p-1.5">
			<span class="sr-only">Your Company</span>
			<svg xmlns="http://www.w3.org/2000/svg" fill="#c24c2c" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class=" h-8 w-8 text-[#c24c2c]">
				<path stroke-linecap="round" stroke-linejoin="round" d="M16.712 4.33a9.027 9.027 0 011.652 1.306c.51.51.944 1.064 1.306 1.652M16.712 4.33l-3.448 4.138m3.448-4.138a9.014 9.014 0 00-9.424 0M19.67 7.288l-4.138 3.448m4.138-3.448a9.014 9.014 0 010 9.424m-4.138-5.976a3.736 3.736 0 00-.88-1.388 3.737 3.737 0 00-1.388-.88m2.268 2.268a3.765 3.765 0 010 2.528m-2.268-4.796a3.765 3.765 0 00-2.528 0m4.796 4.796c-.181.506-.475.982-.88 1.388a3.736 3.736 0 01-1.388.88m2.268-2.268l4.138 3.448m0 0a9.027 9.027 0 01-1.306 1.652c-.51.51-1.064.944-1.652 1.306m0 0l-3.448-4.138m3.448 4.138a9.014 9.014 0 01-9.424 0m5.976-4.138a3.765 3.765 0 01-2.528 0m0 0a3.736 3.736 0 01-1.388-.88 3.737 3.737 0 01-.88-1.388m2.268 2.268L7.288 19.67m0 0a9.024 9.024 0 01-1.652-1.306 9.027 9.027 0 01-1.306-1.652m0 0l4.138-3.448M4.33 16.712a9.014 9.014 0 010-9.424m4.138 5.976a3.765 3.765 0 010-2.528m0 0c.181-.506.475-.982.88-1.388a3.736 3.736 0 011.388-.88m-2.268 2.268L4.33 7.288m6.406 1.18L7.288 4.33m0 0a9.024 9.024 0 00-1.652 1.306A9.025 9.025 0 004.33 7.288" />
			  </svg>
			  
			
		  </div>
		</div>
		<div class="hidden cursor-pointer lg:flex lg:gap-x-12">
		  <div  class="text-sm font-semibold leading-6 hover:text-white text-white">Home</div>
		  <div  class="flex  items-center text-sm font-semibold leading-6 hover:text-white text-[#cac4bc]">Services 
			<svg
                    
                    class="w-4 h-4 ml-2"
                    aria-hidden="true"
                    fill="none"
                    stroke="currentColor"
                    viewBox="0 0 24 24"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M19 9l-7 7-7-7"
                    ></path>
                  </svg>
		  </div>
		  <div  class="text-sm font-semibold leading-6 hover:text-white text-[#cac4bc]">About us</div>
		  <div  class="text-sm font-semibold leading-6 hover:text-white text-[#cac4bc]">Blog</div>
		  		  <div  class="text-sm font-semibold leading-6 hover:text-white text-[#cac4bc]">Career</div>
		</div>	
		<div class="flex w-[300px] flex-2 items-center justify-end gap-x-6">
			{#if visible}
			<button in:fly="{{ y: 200, duration: 400 }}" class="rounded-full font-bold text-[#0c1119] bg-[#40b1ba] py-3 px-10" >
			
			  
				Contact us
			 </button>
			 {/if}
			
		  <button class="flex text-white items-center py-2 px-3 bg-trasparent border-none">
			<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 mr-4">
				<path stroke-linecap="round" stroke-linejoin="round" d="M15.75 5.25a3 3 0 013 3m3 0a6 6 0 01-7.029 5.912c-.563-.097-1.159.026-1.563.43L10.5 17.25H8.25v2.25H6v2.25H2.25v-2.818c0-.597.237-1.17.659-1.591l6.499-6.499c.404-.404.527-1 .43-1.563A6 6 0 1121.75 8.25z" />
			  </svg>
			Login
		</button>
		</div>
		<div class="flex lg:hidden">
		  <button on:click={openMobileMenu} type="button" class="-m-2.5 inline-flex items-center justify-center rounded-md p-2.5 text-gray-700">
			<span class="sr-only">Open main menu</span>
			<svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true">
			  <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" />
			</svg>
		  </button>
		</div>
	  </nav>
	  <!-- Mobile menu, show/hide based on menu open state. -->
	  {#if showMobile}
	  <div class="lg:hidden" role="dialog" aria-modal="true">
		<!-- Background backdrop, show/hide based on slide-over state. -->
		<div class="fixed inset-0 z-10"></div>
		<div class="fixed inset-y-0 right-0 z-10 w-full overflow-y-auto bg-white px-6 py-6 sm:max-w-sm sm:ring-1 sm:ring-gray-900/10">
		  <div class="flex items-center gap-x-6">
			<a href="#" class="-m-1.5 p-1.5">
			  <span class="sr-only">Your Company</span>
			  <img class="h-8 w-auto" src="https://tailwindui.com/img/logos/mark.svg?color=indigo&shade=600" alt="">
			</a>
			<a href="#" class="ml-auto rounded-md bg-indigo-600 px-3 py-2 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600">Sign up</a>
			<button type="button" class="-m-2.5 rounded-md p-2.5 text-gray-700">
			  <span class="sr-only">Close menu</span>
			  <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true">
				<path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
			  </svg>
			</button>
		  </div>
		  <div class="mt-6 flow-root">
			<div class="-my-6 divide-y divide-gray-500/10">
			  <div class="space-y-2 py-6">
				<a href="#" class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-white hover:bg-gray-50">Product</a>
				<a href="#" class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-grey-200 hover:bg-gray-50">Features</a>
				<a href="#" class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-grey-200 hover:bg-gray-50">Marketplace</a>
				<a href="#" class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-grey-200 hover:bg-gray-50">Company</a>
			  </div>
			  <div class="py-6">
				<a href="#" class="-mx-3 block rounded-lg px-3 py-2.5 text-base font-semibold leading-7 text-grey-200 hover:bg-gray-50">Log in</a>
			  </div>
			</div>
		  </div>
		</div>
	  </div>
	  {/if}
</header>

<style>

@keyframes -global-slide-fwd-center {
  0% {
    -webkit-transform: translateZ(0);
            transform: translateZ(0);
  }
  100% {
    -webkit-transform: translateZ(160px);
            transform: translateZ(160px);
  }
}
</style>
