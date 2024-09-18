<script>
	import Card from '$lib/Card.svelte';
	import Picture from '$lib/Picture.svelte';
</script>

<svelte:head>
	<title>Cards</title>
</svelte:head>

<div>
	<form>test</form>

	<Card>
		<div class="text-center text-3xl">Lady Geist</div>
		<div class="flex h-full flex-col gap-4 pt-2">
			<Picture />
			<div class="h-full rounded-lg bg-neutral-800">
				<div class="px-4 py-2">
					Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor
					invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et
					accusam et justo duo dolores et ea rebum.
				</div>
			</div>
		</div>
	</Card>
</div>
