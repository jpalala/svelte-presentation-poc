<script>
	export let imgUrl;
	export let caption;
	let showCaption = false;
	export function toggleCaption() {
		showCaption = !showCaption;
	}
</script>
<style>
	.caption { color: black; font-size: 14px;}
	
	img {
		max-height: 100%;
		max-width: 100%;
		width: auto;
		height: auto;
		top: 0;
		bottom: 0;
		left: 0;
		right: 0;
		margin: auto;
		border: 5px solid black;
	}
	
	.centered {
		top: 25px;
	}
	.slide {
		width:100%;
		height:100vh;
		display: flex;
		align-items: center;
		justify-content: center;
		border-bottom: 2px dotted black;
	}
	
	
</style>
<section class="slide image">
	<button on:click={toggleCaption}>What?</button>
	<figure>
		<img src={imgUrl} alt="slide image" class="centered"  />
		{#if showCaption}
			<figcaption class="caption">{caption}</figcaption>
		{/if}
		
	</figure>
</section>