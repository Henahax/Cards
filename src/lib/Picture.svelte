<script lang="ts">
	interface Props {
		image: string;
		imageColor: string;
	}

	let { image, imageColor }: Props = $props();
</script>

<div id="cardImage" class="h-full rounded-lg bg-neutral-800 p-2" style="--imageColor: {imageColor}">
	{#if image.length > 0}
		<img class="h-full w-full bg-cover rounded-md object-cover" src={image} alt="card" />
	{/if}
</div>

<style>
	#cardImage{
		background-color: var(--imageColor);
	}

	img{
		aspect-ratio: 4 / 3;
	}

</style>
