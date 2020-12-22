<script>
	import Nav from "./Nav.svelte";
	import Header from "./Header.svelte";
	import Article from "./Article.svelte";
</script>

<style type="text/scss">
	.main {
		display: flex;
		flex-direction: column;
		align-items: center;
		width: 100%;
		&__inner {
			display: flex;
			flex-direction: column;
			align-items: center;
			width: 75%;
		}
	}
</style>

<Nav />
<Header />
<main class="main">
	<div class="main__inner">
		<Article />
	</div>
</main>
