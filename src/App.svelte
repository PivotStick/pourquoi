<script>
	import { slide, fade } from "svelte/transition"
	import Page from "./Page.svelte";

	let password = "";
	let isCorrect = false;
	let changePage = false;
	let timeout

	$: {
		isCorrect = password === "Fighting gold"

		if (isCorrect && !timeout && !changePage) {
			timeout = setTimeout(() => {
				changePage = true;
				clearTimeout(timeout)
			}, 3000)
		}
	}
</script>

{#if !changePage}
<main transition:fade>
	{#if isCorrect}
		<h1 transition:slide>Bravo billy 😎</h1>
	{:else}
		<input transition:slide bind:value={password} type="password" placeholder="Un mot de passe ? 🧐">
	{/if}
</main>
{:else}
<Page />
{/if}