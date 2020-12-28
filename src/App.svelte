<script>
	import Nav from "./Nav.svelte";
	import Header from "./Header.svelte";
	import Article from "./Article.svelte";
	import Footer from "./Footer.svelte";
</script>

<style type="text/scss">
	:global(body) {
		background: #fbfbfb;
	}
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
			& p {
				color: #342e37;
			}
		}
	}
	@media screen and (max-width: 900px) {
		.main {
			&__inner {
				display: flex;
				flex-direction: column;
				align-items: center;
				width: 95%;
				& p {
					color: #342e37;
				}
			}
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
<Footer />
