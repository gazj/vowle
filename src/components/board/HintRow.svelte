<script lang="ts">
	import { createEventDispatcher } from "svelte";
	import { COLS } from "../../utils";

	import HintTile from "./HintTile.svelte";
	export let hints: string[];
	export function shake() {
		animation = "shake";
	}
	export function bounce() {
		tiles.forEach((e) => e.bounce());
	}
	const dispatch = createEventDispatcher();
	let animation = "";
	let tiles: Tile[] = [];
</script>

<div
	class="board-hint-row"
	on:animationend={() => (animation = "")}
	data-animation={animation}
>
	{#each hints as hint}
		<HintTile hint={hint} />
	{/each}
</div>

<style lang="scss">
	.board-hint-row {
		display: grid;
		grid-template-columns: repeat(var(--cols), 1fr);
		gap: 5px;
	}
</style>
