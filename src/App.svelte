<script>
	import Form from './components/Form.svelte';
</script>

<main>
	<h2 class="title">Hello</h2>
	<Form />
</main>

<style>
	main {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		gap: 27px;
		height: 100vh;
	}

	.title {
		padding: 0;
		margin: auto 0 0;
		font-size: 55px;
		font-weight: 500;
		line-height: 120%;
		letter-spacing: 0;
		text-align: center;
	}

	@media screen and (max-width: 800px) {
		main {
			gap: 14px;
		}

		.title {
			font-size: 32px;
		}
	}
</style>
