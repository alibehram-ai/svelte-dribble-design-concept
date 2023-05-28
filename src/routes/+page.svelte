<script lang="ts">
	
	import Counter from './Counter.svelte';
	import welcome from '$lib/images/svelte-welcome.webp';
	import welcome_fallback from '$lib/images/svelte-welcome.png';
	import baloon from '$lib/images/baloons.jpg';
	import couch from '$lib/images/couch.jpg';
	import Header from './Header.svelte';
	import beach_save from '$lib/images/life-save-beach.jpeg';
	import bmw from '$lib/images/bmw.png';
	import home from '$lib/images/home.jpg';
	import medicine from '$lib/images/medicine.jpeg';
	import founder from '$lib/images/founder.jpeg';
	import child from '$lib/images/hope.jpeg';
	import { elasticOut } from 'svelte/easing'
	let scrolled = false;
	import { fade, fly, slide } from 'svelte/transition';
let scroll : number;
let transition1: boolean = false;
let carousel: any; // for calling methods of the carousel instance
  
  const handleNextClick = () => {
    carousel.goToNext()
  }

$:{
	console.log("scroll",scroll)
	if (scroll > 10) {
	scrolled = true;
	
  }
  else {	
	scrolled= false;
  }
}
</script>
<svelte:window bind:scrollY={scroll} />
<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>
<link href="https://fonts.googleapis.com/css?family=Anton" rel="stylesheet">

<Header visible={scrolled}/>

<section class="px-10 ">

	
	{#if scroll >20 }
	<div class="mt-10 flex"  in:fly="{{ y: 200, duration: 1000 }}" out:slide="{{duration: 1000}}">
		<div class="ml-5 first-text text-[#cac4bc] w-1/2">Darcy's Insurance Products</div>
		<div class="flex gap-x-40 second-text">
			<div class="flex flex-col justify-start">
				<div class="my-5 flex-col justify-start items-start">
					<!-- star -->
					<div class="mt-2 mb-4 rounded-full bg-white w-12 h-12 flex justify-center items-center"> 
						<svg xmlns="http://www.w3.org/2000/svg"  fill="currentColor" class="w-8 rounded-full h-8  text-[#0c0f17]" viewBox="0 0 24 24"><path d="M12 .587l3.668 7.568 8.332 1.151-6.064 5.828 1.48 8.279-7.416-3.967-7.417 3.967 1.481-8.279-6.064-5.828 8.332-1.151z"/></svg>
						
					</div>
					<div class="ml-2 sub-font text-sm text-[#cac4bc]">Our <span class="text-[#40b1ba] w-1/2 underline">plans</span> are saving <br> policyholders 30% - 60% <br> on premiums</div>
				</div>
				<div class="my-5">
					<div class="mt-2 mb-4 rounded-full bg-white w-12 h-12 flex justify-center items-center"> 
						<svg xmlns="http://www.w3.org/2000/svg"  fill="currentColor" class="w-8 rounded-full h-8  text-[#0c0f17]" viewBox="0 0 24 24"><path d="M12 .587l3.668 7.568 8.332 1.151-6.064 5.828 1.48 8.279-7.416-3.967-7.417 3.967 1.481-8.279-6.064-5.828 8.332-1.151z"/></svg>
						
					</div>
					<div class="ml-2 sub-font text-sm text-[#cac4bc]">We offer a choice of low <br>dedactibies and include <br>no-cost value added <br>services</div>
				</div>
				<div class="w-[80px] h-[180px] flex justify-center items-center rounded-full bg-gradient-custom">
					<svg fill="#cac4bc" height="300px" width="300px" version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 330 330" xml:space="preserve" stroke="#cac4bc"><g id="SVGRepo_bgCarrier" stroke-width="0"></g><g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g><g id="SVGRepo_iconCarrier"> <path id="XMLID_24_" d="M216.358,271.76c-2.322-5.605-7.792-9.26-13.858-9.26H180V15c0-8.284-6.716-15-15-15 c-8.284,0-15,6.716-15,15v247.5h-22.5c-6.067,0-11.537,3.655-13.858,9.26c-2.321,5.605-1.038,12.057,3.252,16.347l37.5,37.5 C157.322,328.536,161.161,330,165,330s7.678-1.464,10.607-4.394l37.5-37.5C217.396,283.816,218.68,277.365,216.358,271.76z"></path> </g></svg>
					  
				</div>
			</div>
			<div class="flex my-5 justify-end items-center">
			<img src={baloon} alt="baloon" class="w-[200px] custom-class h-full rounded-[150px]">
			</div>
		</div>
	</div>
	{/if}
	{#if scroll > 250}
	<div class="my-20 flex flex-row gap-x-8" in:fly="{{ x: 200, duration: 1000 }}" out:fade="{{duration: 1000}}">
		<div class="basis-1/2 shadow hover:custom-class  shadow-[#401bc]" in:fly="{{ x: 300, duration: 1000 }}">
			<div class="relative">
				<img src={couch} alt="couch" class=" w-full h-[380px] rounded-[50px]">
				<div class="absolute top-[75%] left-2 bg-[#0c1119] text-[#cac4bc] text-lg font-bold rounded-full py-5 px-8	">Home Insurance	</div>
			</div>
			
		</div>
		<div class="basis-1/5" in:fly="{{ x: 500, y:300, duration: 1000 }}">
			<img src={beach_save} alt="baloon" class="w-[200px] custom-class h-full rounded-[150px]">
		</div>
		<div class="basis-2/5" in:fly="{{ x: 600, y:500, duration: 1000 }}">
			<div class="h-[380px] w-full rounded-[50px] bg-[#0e1d31] p-10 ">
				<div class="custom-text-family text-[#cac4bc] ">Best choice</div>
				<div class="mt-10 sub-font text-sm text-[#cac4bc]">Not all insurances are the same that's <br>why agnecy knows that your insurance <br>should be customized to fit your <br>situation</div>
				<div class="mt-[60px] bg-[#eb6574] px-5 py-3 flex justify-center rounded-full text-lg font-bold">View all services</div>
			</div>
		</div>
	</div>
	{/if}
	{#if scroll > 500}
	<div class="flex flex-row mt-10 gap-x-8"  in:fly="{{ x: 200, duration: 1000 }}" out:slide="{{duration: 1000}}">
		<div class="" in:fly="{{ x: 700, y:600, duration: 1000 }}">
			<div class="relative">
				<img src={bmw} alt="couch" class=" w-[400px] h-[300px] rounded-[50px]">
				<div class="absolute top-[70%] left-2 bg-[#0c1119] text-[#cac4bc] text-lg font-bold rounded-full py-4 px-5	">Vehicle Damage	</div>
			</div>
			
		</div>
		<div class="" in:fly="{{ x: 800, y:700, duration: 1000 }}">
			<div class="relative">
				<img src={home} alt="couch" class=" w-[400px] h-[300px] rounded-[50px]">
				<div class="absolute top-[70%] left-2 bg-[#0c1119] text-[#cac4bc] text-lg font-bold rounded-full py-4 px-5	">Mortgage Insurance	</div>
			</div>
			
		</div>
		<div class="">
			<div class="relative" in:fly="{{ x: 850, y:750, duration: 1000 }}">
				<img src={medicine} alt="couch" class=" w-[400px] h-[300px] rounded-[50px]">
				<div class="absolute top-[70%] left-2 bg-[#0c1119] text-[#cac4bc] text-lg font-bold rounded-full py-4 px-5	">Medical Expenses	</div>
			</div>
			
		</div>
	</div>
	{/if}
	{#if scroll > 1200}
	<div class="my-20 flex flex-row gap-x-10" in:fly="{{ x: 200, duration: 1000 }}" out:slide="{{duration: 1000}}">
		<div class="basis-5/6" in:fly="{{ x: 850, y:750, duration: 1000 }}">
			
				
				<div class="w-[900px] bg-[#0e1d31] rounded-[50px] flex gap-x-10 flex-row p-10">
					<div class="basis-1/3 justify-start">
						
						<div class=" ml-10 w-[300px] h-[600px]">
							<img src={founder} alt="baloon" class="w-full h-full rounded-[150px]">
							</div>
						</div>
						
					<div class="basis-1/2 justify-end">
						<div class="text-3xl text-[#cac4bc] mt-10 font-bold ">
							Georgia Darcy
						</div>
						<div class="text-lg text-[#344354] my-10  ">The Agency Founder </div>
						<div class="text-sm text-[#cac4bc] my-10">
							Georgia Darcy is the founder and CEO of a successful insurance company, renowned for its innovative solutions and customer-centric approach. With over 20 years of experience in the industry, she has built a reputation on her deep knowledge of insurance products, exceptional leadership skills, and strategic thinking. Under her leadership, the company has consistently achieved remarkable growth, and has become a frontrunner in the industry. Ms. Darcy is also known for her commitment to giving back to the community, and regularly supports charitable causes. Her vision and dedication have made her a respected figure in the insurance sector, and an inspiration for aspiring entrepreneurs.	
						</div>
						<div class="px-8 py-4 rounded-full text-xl text-[#344354] bg-[#81c0d0] flex justify-center">Get a consultation</div>
					</div>
					
				</div>
				<div class="flex justify-center">
					<div class="my-5 text-center flex space-x-3 bottom-5 ">
						<button type="button" class="w-3 h-3 bg-white rounded-full" ></button>
						<button type="button" class="w-3 h-3 bg-[#cac4bc] rounded-full" ></button>
						<button type="button" class="w-3 h-3 bg-[#cac4bc] rounded-full" ></button>
						<button type="button" class="w-3 h-3 bg-[#cac4bc] rounded-full" ></button>
						<button type="button" class="w-3 h-3 bg-[#cac4bc] rounded-full"></button>
					</div>
				</div>
			
		</div>
		<div class="flex justify-end items-start">
			<div class="ml-10 mt-[205px] mb-4 rounded-full bg-[#cac4bc] w-12 h-12 flex justify-center items-center"> 
				<svg xmlns="http://www.w3.org/2000/svg"  fill="currentColor" class="w-8 rounded-full h-8  text-[#0c0f17]" viewBox="0 0 24 24"><path d="M12 .587l3.668 7.568 8.332 1.151-6.064 5.828 1.48 8.279-7.416-3.967-7.417 3.967 1.481-8.279-6.064-5.828 8.332-1.151z"/></svg>
				
			</div>
			<div class="mt-[200px] ml-4 our-experts-text text-[#cac4bc]">Our <br> experts <br> say</div>
			
		</div>
	</div>
	{/if}
	{#if scroll > 1900}
	<div class="flex flex-row p-20 gap-x-[180px]" in:fly="{{ x: 200, duration: 1000 }}" out:slide="{{duration: 1000}}" >
		<div class="flex justify-start items-center">
			<div class="our-experts-text text-[#cac4bc]">Support <br> at every <br> <span class="text-[100px]">Step</span></div>
		</div>
		<div class="flex flex-col justify-start">
			<div class="my-5 flex-col justify-start items-start">
				<!-- star -->
				<div class="mt-2 mb-4 rounded-full bg-white w-12 h-12 flex justify-center items-center"> 
					<svg xmlns="http://www.w3.org/2000/svg"  fill="currentColor" class="w-8 rounded-full h-8  text-[#0c0f17]" viewBox="0 0 24 24"><path d="M12 .587l3.668 7.568 8.332 1.151-6.064 5.828 1.48 8.279-7.416-3.967-7.417 3.967 1.481-8.279-6.064-5.828 8.332-1.151z"/></svg>
					
				</div>
				<div class="ml-2 sub-font text-sm text-[#cac4bc]">Participate in the <span class="text-[#40b1ba] w-1/2 underline">loyalty program</span>.Pay for the <br>service online to get bonuses for our other <br>services. We have a lot of bonuses</div>
			</div>
			<div class="my-5">
				<div class="mt-2 mb-4 rounded-full bg-white w-12 h-12 flex justify-center items-center"> 
					<svg xmlns="http://www.w3.org/2000/svg"  fill="currentColor" class="w-8 rounded-full h-8  text-[#0c0f17]" viewBox="0 0 24 24"><path d="M12 .587l3.668 7.568 8.332 1.151-6.064 5.828 1.48 8.279-7.416-3.967-7.417 3.967 1.481-8.279-6.064-5.828 8.332-1.151z"/></svg>
					
				</div>
				<div class="ml-2 sub-font text-sm text-[#cac4bc]">You can help other people: choose a donation <br>fund and share the link with your friend!</div>
			</div>
			<div class="border-[#ff6476] text-[#ff6476] text-bold text-xl border rounded-full bg-transparent px-6 py-3 flex justify-center ">Choose a fund </div>
		</div>
		<div class="flex my-5 justify-end items-center">
			<img src={child} alt="baloon" class="w-[300px] h-[400px]custom-class h-full rounded-[150px]">
			</div>
	</div>
	{/if}
</section>
<style lang="postcss">
	 :global(html) {
    background-color: theme(colors.gray.100);
  }
  .custom-class{
	box-shadow: 1px 3px 10px #cac4bc, 1px 3px 30px #40b1ba;
  }
  .bg-gradient-custom {
		background: linear-gradient(to bottom, #0d121c 0% ,#151b29 80%);
	}
	@font-face {
    font-family: 'Blomine';
    font-style: normal;
    src: local('Blomine'), local('Blomine'), url('/static/fonts/blimone-bold-inktrap.ttf') format('ttf');
    
}
.first-text{
		font-family: 'Anton';
		font-size: 120px;
		
	}
	.custom-text-family{
		font-family: 'Anton';
		font-size: 40px;
	}
	.our-experts-text{
		font-family: 'Anton';
		font-size: 80px;
		line-height:1.2 !important;

	}
.sub-font{
}
</style>
