<script lang="ts">
	import { COLS, ROWS } from "../../utils";

	import { Tile } from "../board";
	import HintRow from "../board/HintRow.svelte";
	export let visible: boolean;
	export let hints = [
		"consonant",
		"consonant",
		"vowel",
		"consonant",
		"vowel",
	];
</script>

<h3>how to play</h3>
<div>Guess the word in {ROWS} tries.</div>
<div>Each guess must be a valid {COLS} letter word. Hit the enter button to submit.</div>
<div>
	After each guess, the color of the tiles will change to show how close your guess was to the
	word.
</div>
<div>
	Unlike original Wordle, Vowle gives you a hint by showing which letters are consonants and which are vowels.
</div>
<div class:complete={visible} class="examples" style="--cols: {COLS}">
	<div><strong>Examples</strong></div>
	<div>The colors above each column show the positions of consonants and vowels in the target word. Blue represents a consonant in the given column, and pink represents a vowel.</div>
	<HintRow hints={hints} />
	<div>If the word were SPACE, the example above is how the hint row would look.</div>
	<div><strong>Note:</strong> 'Y' is not considered a vowel in this game.</div>
	<div class="row">
		<Tile value="w" state="🟩" />
		<Tile value="e" state="🔳" />
		<Tile value="a" state="🔳" />
		<Tile value="r" state="🔳" />
		<Tile value="y" state="🔳" />
	</div>
	<div>The letter <strong>W</strong> is in the word and in the correct spot.</div>
	<div class="row">
		<Tile value="p" state="🔳" />
		<Tile value="i" state="🟨" />
		<Tile value="l" state="🔳" />
		<Tile value="l" state="🔳" />
		<Tile value="s" state="🔳" />
	</div>
	<div>The letter <strong>I</strong> is in the word but in the wrong spot.</div>
	<div class="row">
		<Tile value="v" state="🔳" />
		<Tile value="a" state="🔳" />
		<Tile value="g" state="🔳" />
		<Tile value="u" state="⬛" />
		<Tile value="e" state="🔳" />
	</div>
	<div>The letter <strong>U</strong> is not in the word in any spot.</div>
</div>
<div>
	This is a variation of the original <a
		href="https://www.nytimes.com/games/wordle/"
		target="_blank"
		rel="noreferrer">Wordle</a
	>
	by Josh Wardle with additional modes and features, allowing you to play infinite Wordles.
	Switch to infinite mode to play an unlimited number of times.
	<br /><br />
	Open the settings menu to see some of the additional features.
	<br />
	Written with Svelte, in Typescript by
	<a href="https://github.com/MikhaD" target="_blank" rel="noreferrer">MikhaD</a>, and ported by
	<a href="https://github.com/gazj" target="_blank" rel="noreferrer">Gaz J.</a>.
</div>

<style lang="scss">
	div {
		margin: 14px 0;
	}
	.examples {
		border-top: 1px solid var(--border-primary);
		border-bottom: 1px solid var(--border-primary);
		:global(.row > *) {
			height: 100%;
			aspect-ratio: 1;
		}
		&:not(.complete) :global(.row .back) {
			transition-delay: 0.3s;
		}
	}
	.row {
		height: 40px;
		display: flex;
		gap: 4px;
	}
	.row.tutorial-hint-row {
		height: 10px;
	}
	.row.tutorial-hint-row .board-hint-tile {
		aspect-ratio: 4 !important;
	}
</style>
