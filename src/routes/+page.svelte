<script>
	import Card from '$lib/Card.svelte';
	import Picture from '$lib/Picture.svelte';

	let {
		title = 'Card Name',
		text = 'Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum.',
		cardType = '1',
		image = 'https://gratisography.com/wp-content/uploads/2024/01/gratisography-cyber-kitty-800x525.jpg',
		cardColor = '#000000',
		borderColor = '#ffffff',
		textColor = '#ffffff',
		imageColor = '#ffffff'
	} = $props();
</script>

<svelte:head>
	<title>Cards</title>
</svelte:head>

<div class="flex flex-row gap-4">
	<form class="grid h-fit grid-cols-2 gap-4 p-4">
		<label for="cardColor">card color</label>
		<input type="color" id="cardColor" class="w-full" bind:value={cardColor} />
		<label for="borderColor">card border color</label>
		<input type="color" id="borderColor" class="w-full"bind:value={borderColor} />
		<label for="textColor">text color</label>
		<input type="color" id="cardColor" class="w-full" bind:value={textColor} />
		<label for="title">card title</label>
		<input id="title" class="input input-bordered" bind:value={title} />
		<label for="cardType">card type</label>
		<select id="cardType" class="select select-bordered" bind:value={cardType}>
			<option value="1">Picture</option>
			<option value="2">Full Text</option>
		</select>
		{#if cardType === '1'}
			<label for="image">image path</label>
			<input id="image" class="input input-bordered" bind:value={image} />
			<label for="imageColor">image border</label>
			<input type="color" id="imageColor" class="w-full" bind:value={imageColor} />
		{/if}
		<label for="text">card text</label>
		<textarea id="text" class="textarea textarea-bordered" bind:value={text}></textarea>
	</form>

	<Card {borderColor} {cardColor} {textColor}>
		{#if cardType === '1'}
			<div class="text-center text-3xl">{title}</div>
		{/if}

		<div class="flex h-full flex-col gap-4 pt-2">
			{#if cardType === '1'}
				<Picture {image} {imageColor} />
			{/if}

			<div class="flex h-full flex-col rounded-lg grow" class:justify-center={cardType === '2'}>
				{#if cardType === '2'}
					<div class="text-center text-3xl">{title}</div>
				{/if}

				<div class="px-4 py-2 text-justify mx-auto" class:mx-4={cardType === '2'}>
					{text}
				</div>
			</div>
		</div>
	</Card>
</div>

<style>
</style>
