<script>
	import prompts from '$lib/data/prompts.json';

	function getWord( type ) {
		const words = prompts[type];
		const rand = Math.floor(Math.random() * words.length)
		return words[rand];
	}
</script>

<h1>"Find the <mark>{getWord('noun')}</mark> and stop the <mark>{getWord('villain')}</mark> from <mark>{getWord('action')}</mark> <mark>{getWord('target')}</mark> before <mark>{getWord('time')}</mark>!"</h1>

<style>
	h1 {
		color: black;
		font-size: clamp(1.5rem, 3vw + 1rem, 3.265rem);
		text-align: center;
		max-width: 70rem;
		padding: 0 30px;
		margin: 0;
		margin-bottom: clamp(2rem, 2vw + 1rem, 4rem);
		line-height: 1.5;
		text-transform: lowercase;
	}
	mark {
		background-color: rgb(255,231,25);
		border: 5px solid rgb(230,244,252);
		margin: 0;
	}
</style>
