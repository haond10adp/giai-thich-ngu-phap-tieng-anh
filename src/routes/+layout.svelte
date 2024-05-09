<script>
	import '../app.css';
	let { children } = $props();
</script>

<nav>
	<ul>
		<li><a href="/">Home</a></li>
	</ul>
</nav>
{@render children()}
