<script>
	import Text from '$lib/Text.svelte';
	import morkBorgLogo from '$lib/assets/CompWith_MORKBORG_horiz.svg';

	const restart = () => {
		location.reload();
	}
</script>

<header>
	<Text/>
</header>
<main>
	<button class="flag-shape" on:click={restart}><span>hard pass</span></button>
</main>
<footer>
	<p>An adventure generator for <a href="https://morkborg.com/content/" title="Mörk Borg RPG">Mörk Borg</a> by <a href="https://curren.me" title="Mike Curren Freelance Web Developer">michaelopolis</a>.</p>
	<a href="https://morkborg.com/content/" title="Mörk Borg RPG"><img src="{morkBorgLogo}" alt="Compatible with Mörk Borg" /></a>
</footer>

<style>
@import url('https://fonts.googleapis.com/css2?family=New+Rocker&display=swap');
:global(html) {
	box-sizing: border-box;
	-moz-text-size-adjust: none;
	-webkit-text-size-adjust: none;
	text-size-adjust: none;
	font-size: 18px;
}
:global(*, *:before, *:after) {
	box-sizing: inherit;
	letter-spacing: inherit;
}
:global(body) {
	margin: 0;
	background: rgb(230,244,252) url('$lib/assets/grit.png') no-repeat;
	background-size: cover;
	font-family: system-ui, "Segoe UI", Roboto, Helvetica, Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol";
}
:root {
	--space: clamp(0.75rem, 2vw + 0.5rem, 4rem);
	--space-half: clamp(0.75rem, 1vw + 0.5rem, 2rem);
	--color-red: rgb(230, 11, 11);
}
p {
	line-height: 1.5;
	margin: 0.75rem 0;
}
a {
	/* text-decoration: none; */
	color: inherit;
	transition: color 0.3s ease, fill 0.3s ease;
}
a:hover {
	color: var(--color-red);
}
header,
main,
footer {
	margin: var(--space) auto;
	padding: 0 var(--space);
}
header,
main {
	font-family: 'New Rocker', cursive;
	letter-spacing: 0.0875rem;
}
header,
footer {
	margin-top: auto;
}
header {
	margin-top: auto;
}
main {
	margin: 0 auto;
}
footer {}
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
	background: var(--color-red);
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
footer {
	display: grid;
	width: 100%;
	place-items: center;
	gap: 0;
	font-weight: 500;
}
footer > p {
	text-align: center;
	margin-bottom: 0;
}
footer > a {
	grid-area: 1 / 1;
}
footer img {
	width: 120px;
}
@media (min-width: 50rem) {
	footer {
		grid-template-columns: auto 1fr;
		grid-template-rows: 1fr;
		justify-items: stretch;
		place-items: center / start;
	}
	footer > p {
		text-align: left;
		grid-area: 1;
		margin: 0;
	}
	footer > a {
		justify-self: end;
		grid-area: 1 / 2;
	}
	footer img {
		width: 120px;
	}
}
</style>
