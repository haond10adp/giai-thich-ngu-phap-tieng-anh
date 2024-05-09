<script lang="ts">
	type Options = 'C' | 'U';
	type Word = [string, Options];
	let picked: Options[] = $state([]);
	const words: Word[] = [
		['car', 'C'],
		['work', 'U'],
		['news', 'U'],
		['meat', 'U'],
		['photo', 'C'],
		['golf', 'U'],
		['banana', 'C'],
		['rice', 'U'],
		['song', 'C'],
		['minute', 'C'],
		['music', 'U'],
		['flower', 'C'],
		['money', 'U'],
		['ship', 'C'],
		['advice', 'U'],
		['love', 'U'],
		['furniture', 'U'],
		['electricity', 'U'],
		['water', 'U'],
		['meal', 'C']
	];
</script>

<h2>I. Look at these nouns. Are they countable (C) or uncountable (U)</h2>
<ul>
	{#each words as word, key}
		<li>
			<span class="word">{word[0]}</span>
			<div>
				<label for="c{key}">
					<input id="c{key}" bind:group={picked[key]} type="radio" value="C" />
					C
				</label>

				<label for="u{key}">
					<input id="u{key}" bind:group={picked[key]} type="radio" value="U" />
					U
				</label>
			</div>
			<span>
				{#if word[1] == picked[key]}
					✅ {word[1] == 'C' ? 'Countable' : 'Uncountable'}
				{:else if !picked[key]}{:else}
					❌
				{/if}
			</span>
		</li>
	{/each}
</ul>

<style>
	ul {
		width: 50ch;
	}
	ul li {
		display: flex;
		line-height: 1.75em;
		font-size: larger;
	}

	ul li:nth-child(2n + 1) {
		background-color: gainsboro;
	}
	span.word {
		width: 10ch;
	}
	div {
		margin-right: 1em;
	}

	label:hover {
		border: 1px dashed;
		cursor: pointer;
	}
</style>
