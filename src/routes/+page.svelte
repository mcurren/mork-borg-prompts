<script>
	import Text from '$lib/Text.svelte';

	const restart = () => {
		location.reload();
	}
</script>

<div>
	<Text/>
	<button class="flag-shape" on:click={restart}><span>hard pass</span></button>
</div>

<style>
	@import url('https://fonts.googleapis.com/css2?family=New+Rocker&display=swap');
	:global(html) {
		box-sizing: border-box;
		-moz-text-size-adjust: none;
		-webkit-text-size-adjust: none;
		text-size-adjust: none;
	}
	:global(*, *:before, *:after) {
		box-sizing: inherit;
		letter-spacing: inherit;
	}
	:global(body) {
		margin: 0;
		background: rgb(230,244,252) url('$lib/assets/grit.png') no-repeat;
  	background-size: cover;
		font-family: 'New Rocker', cursive;
		font-size: 62.5%;
		letter-spacing: 0.0875rem;
	}
	div {
		width: 100%;
		height: 100vh;
		display: flex;
		align-items: center;
		justify-content: center;
		flex-direction: column;
	}
	button {
		background: black;
		border: 0;
		border-radius: 0;
		color: white;
		font-family: inherit;
		text-transform: lowercase;
		font-size: 1.3rem;
		padding: 0.3rem 0.5rem;
		transition: all 0.3s;
		cursor: pointer;
	}
	button:hover,
	button:focus,
	button:active {
		background: rgb(230, 11, 11);
	}
	button:active {
		transform: translateY(5px);
	}
	.flag-shape {
		width: 130px;
		height: 56px;
		box-sizing: content-box;
		padding: 7px 5px 15px;
		position: relative;
		text-align: center;
	}
	.flag-shape:after {
		content: "";
		position: absolute;
		left: 0;
		bottom: 0;
		width: 0;
		height: 0;
		border-bottom: 10px solid rgb(230,244,252);
		border-left: 70px solid transparent;
		border-right: 70px solid transparent;
	}
</style>
