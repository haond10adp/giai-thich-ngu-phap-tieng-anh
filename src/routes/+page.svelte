<script>
	import { romanize } from '$lib/romanize';
</script>

<h1>Bài tập ngữ pháp tiếng anh</h1>

{#snippet list(length, folder)}
	<ol>
		{#each Array.from(Array(length).keys()) as item}
			<li><a href="{folder}/ex{item + 1}">{romanize(item + 1)}</a></li>
		{/each}
	</ol>
{/snippet}

<h2>Từ loại (parts of speech)</h2>
<ul>
	<li>
		<h3>Danh từ (Nouns)</h3>
		{@render list(13, 'nouns')}
	</li>
	<li>
		<h3>Đại từ (Pronouns)</h3>
		{@render list(10, 'pronouns')}
	</li>
</ul>

<h2>Thì và sự phối thì (tenses and sequence of tenses)</h2>

<style>
	:global(li) {
		list-style-type: none;
	}
	ol li {
		display: inline-block;
		margin-right: 2ch;
	}
	ol {
		padding-left: 0;
	}
	ul {
		padding-left: 2ch;
	}
</style>
