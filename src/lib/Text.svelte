<script>
import prompts from '$lib/data/prompts.json';

function getPrompt( type ) {
	const words = prompts[type];
	const rand = Math.floor(Math.random() * words.length)
	return words[rand];
}

function changePrompt( type ) {
	hook[type] = getPrompt(type);
}

let hook = {
	noun: getPrompt('noun'),
	villain: getPrompt('villain'),
	action: getPrompt('action'),
	target: getPrompt('target'),
	time: getPrompt('time'),
};
</script>

<h1>
	Find the
	<mark><button on:click={() => changePrompt('noun')}>{hook.noun}</button></mark>
	and stop the
	<mark><button on:click={() => changePrompt('villain')}>{hook.villain}</button></mark>
	from
	<mark><button on:click={() => changePrompt('action')}>{hook.action}</button></mark>
	the
	<mark><button on:click={() => changePrompt('target')}>{hook.target}</button></mark>
	before
	<mark><button on:click={() => changePrompt('time')}>{hook.time}</button></mark>
</h1>

<style>
	h1 {
		color: black;
		font-size: clamp(1.5rem, 3vw + 1rem, 3.265rem);
		text-align: center;
		max-width: 40ch;
		margin: 0;
		line-height: 1.5;
		text-transform: lowercase;
	}
	/* h1:before {
		content: '\201C';
	}
	h1:after {
		content: '!\201D';
	} */
	mark {
		display: inline-block;
		position: relative;
		white-space: nowrap;
		background: none transparent;
	}
	mark:after {
		content: '';
		position: absolute;
		top: 0;
		right: -0.0625em;
		bottom: 0;
		left: -0.0625em;
		z-index: -1;
		background: rgb(255,231,25);
		background: linear-gradient(180deg, rgba(255,255,255,0) 37%, rgba(255,231,25,1) 37%, rgba(255,231,25,1) 76%, rgba(255,255,255,0) 76%);
		opacity: 1;
		transition: opacity 0.4s;
	}
	mark:hover {
		color: rgb(230, 11, 11);
	}
	mark:hover:after {
		opacity: 0;
	}
	button {
		border: none;
		padding: 0;
		margin: 0;
		font: inherit;
		background: none transparent;
		color: inherit;
		cursor: pointer;
		transition: color 0.4s;
	}
</style>
