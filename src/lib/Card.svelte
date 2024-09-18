<div class="Card flex w-96 flex-col rounded-2xl bg-white p-2">
	<div class="flex h-full w-full flex-col rounded-xl bg-blue-700 p-4 pt-2">
		<slot />
	</div>
</div>

<style>
	.Card {
		aspect-ratio: 63 / 88;
	}
</style>
