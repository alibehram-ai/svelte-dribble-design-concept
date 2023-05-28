<script lang="ts">

	
	import './styles.css';
	import "../app.css";
	let scrolled = false;
let scroll : number;


$:{
	console.log("scroll",scroll)
	if (scroll > 10) {
	scrolled = true;
  } else {
	scrolled = false;
  }
}
</script>

<!-- svelte-ignore non-top-level-reactive-declaration -->
<!-- svelte-ignore non-top-level-reactive-declaration -->
<svelte:window bind:scrollY={scroll} />
<div class="p-10">
	<div class=" rounded-[50px] px-10 bg-[#0c0f17] py-10 h-[480vh]" >
		<!-- //bg-gradient-to-b from-[#0d1c30]  via-[#0c1119]  to-[#0c1119] to-90% -->
		<div class=" bg-[#0c0f17] custom-layout rounded-[50px] font-sans w-full h-auto"   class:bg-gradient-custom={scrolled}>
			<!-- <div class="bg-pattern-custom absolute w-full  h-full    bg-repeat"> -->
			
		
			<!-- </div>	 -->
			
			<!-- <img src={Image} alt="bg" class=" absolute w-full  lg:h-full md:h-[75%] sm:h-auto h-[50%]  bg-contain bg-repeat"/>	  -->
			
			
			<main >
				<slot />
			</main>
		
			<footer>
				
			</footer>
		</div>
	</div>
</div>



<style>
	.bg-gradient-custom {
		background: linear-gradient(to bottom, #0d1c30 0% ,#0c0f17 80%);
	}
	@keyframes -global-from-left {
  0% {
    transform: rotateX(50deg) translateX(-200vw) skewX(-50deg);
    opacity: 1;
  }
  100% {
    transform: rotateX(0deg) translateX(0) skewX(0deg);
    opacity: 1;
  }
}
</style>
