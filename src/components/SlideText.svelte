<script>
	export let notes;
	let showNotes;
	import { displayNotes } from '../store.js';
	
	
	export function toggleNotes() {
		showNotes = !showNotes;
		if(showNotes) {
			$displayNotes = 'show';
		} else {
			$displayNotes = 'hidden';
		}
	}
	
</script>
<style>
	.textonly { 
		font-size: 100px;
		color:red;
	}
	
	.textonly span.speakernotes {
		font-size:10px;
		color: grey;
	}
	button.small {
		font-size:10px !important; 
	}
	
	.speakernotes { font-size: 12px}
	
	.top-right {
		position: static;
		top: 0px;
		right: 0px;
	}
</style>
<section class="slide textonly">
	
	
	<div class="top-right">
	<button class="small top-right" on:click={toggleNotes}>
		{#if ($displayNotes == 'hidden') }
		  ? 
		{:else}
		  &times;
		{/if}
	</button>
	</div>
	<center>
		<slot></slot>
	{#if $displayNotes !== 'hidden'}
		<span class="speakernotes" on:click="{toggleNotes}">{notes}</span>
	{/if}
	
	</center>
</section>