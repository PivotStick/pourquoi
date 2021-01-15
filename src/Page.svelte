<script>
    let date = "30 Février, 14h à la comédie"
</script>

<main>
	<h1>Les choses que vous cherchez sont parfois sous vos yeux...</h1>
    <h2>Même si elles ne sont pas forcément toujours visibles</h2>
    
    <p id="secret">{date}</p>
</main>

<style>
	main {
		padding: 0 30vw;
		
		animation: fadein 2000ms cubic-bezier(0.79,-0.01, 0.04, 1.06) forwards;
	}

	main > * {
		cursor: default;
		transition: 300ms cubic-bezier(0.79,-0.01, 0.04, 1.06) transform;
	}

	main > *:hover {
		transform: scale(1.1);
	}

	main > *:not(:last-child) {
		margin-bottom: 1em;
    }
    
    #secret {
        cursor: help;
        position: fixed;

        top: 10vh;
        right: 30vw;
        opacity: 0;

        transition: 400ms cubic-bezier(0.79,-0.01, 0.04, 1.06);
        transition-property: transform, opacity;
    }

    #secret:hover {
        transform: scale(1.1);
        opacity: 1;
    }

    #secret:active {
        transform: scale(0.9);
        opacity: .5;
    }

	@keyframes fadein {
		0% {
			transform: scale(1.2);
			opacity: 0;
		}
		50% { opacity: 1 }
		100% { transform: scale(1) }
	}
</style>