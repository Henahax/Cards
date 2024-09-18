<script lang="ts">
	interface Props {
		borderColor: string;
		cardColor: string;	
		textColor: string;	
	}

	let { cardColor, borderColor, textColor }: Props = $props();
</script>

<div id="Border" class="m-8 flex w-96 flex-col rounded-2xl p-3" style="--borderColor: {borderColor}; --textColor: {textColor}">
	<div id="Card" class="flex h-full w-full flex-col rounded-xl p-4 pt-2" style="--cardColor: {cardColor}">
		<slot/>
	</div>
</div>

<style>
	#Border {
		aspect-ratio: 3 / 5;
		background-color: var(--borderColor);
	}

	#Card{
		background-color: var(--cardColor);
		color: var(--textColor);
	}
</style>
