<script>
	import prompts from '$lib/data/prompts.json';

	function getWord( type ) {
		const words = prompts[type];
		const rand = Math.floor(Math.random() * words.length)
		return words[rand];
	}
</script>

<h1>"Find the <mark data-type="noun">{getWord('noun')}</mark> and stop the <mark data-type="villain">{getWord('villain')}</mark> from <mark data-type="action">{getWord('action')}</mark> <mark data-type="target">{getWord('target')}</mark> before <mark data-type="time">{getWord('time')}</mark>!"</h1>

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
		position: relative;
		white-space: nowrap;
		background: none transparent;
	}
	mark:after {
		content: '';
		position: absolute;
		top: 0;
		right: -0.03125em;
		bottom: 0;
		left: -0.03125em;
		z-index: -1;
		background: rgb(255,231,25);
		background: linear-gradient(180deg, rgba(255,255,255,0) 37%, rgba(255,231,25,1) 37%, rgba(255,231,25,1) 76%, rgba(255,255,255,0) 76%);
	}
</style>
