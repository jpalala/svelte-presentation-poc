<script>
	import IntersectionObserver from './components/IntersectionObserver.svelte';
	import SlideImg from './components/SlideImg.svelte';
	import SlideText from './components/SlideText.svelte';
	import {displayNotes} from './store.js';

	export let name;
	
	function handleKeydown(event) {
		if(event.key === 'Escape') {
			console.log('esc!');
			//updates the reactive displayNotes store (state container)
			$displayNotes = 'hidden';  
		}
	}
		
</script>
<style>

	.content{
		text-align:center;
		width: 70vw;
		background : #efefef;
	}
	
	
</style>

<svelte:window on:keydown={handleKeydown} />

<IntersectionObserver let:intersecting top={400}>
{#if intersecting}
      <SlideImg imgUrl="sup_cheezburger.jpg" caption="I just want to show the cheezburger here"  /> 
{:else}
	<p>You won't see this normally..</p>
{/if}
</IntersectionObserver>

<IntersectionObserver let:intersecting top={400}>
{#if intersecting}
      <SlideText notes="I guess I want to explain about blah and sleep">
		<div class="content">Explain blah</div>
	  </SlideText>
{:else}
	<p>You won't see this normally..</p>
{/if}
</IntersectionObserver>