<script>
import Button from '../components/DarkMode.svelte';
import { MoonIcon, SunIcon } from 'svelte-feather-icons';

let isDarkMode;

</script>

<style>
	nav {
		/* border-bottom: 1px solid rgba(255,62,0,0.1); */
		font-weight: 300;
		display: flex;
		justify-content: space-between;
		padding: 2em;
		/* margin: 0 auto; */
		align-items: center;
	}

	.nav-links {
		display: flex;
		align-items: center;
	}


	a {
		text-decoration: none;
		padding-right: 1em;
		display: block;
	}

	a:hover {
		transform: scale(1.1);
		text-decoration: underline;
		text-decoration-color: #ff2592;
	}

	.brand {
		font-size: 2.5rem;
		font-weight: 700;
		font-family: "News Cycle", sans-serif;

	}

	.brand:hover {
		text-decoration: none;
	}

	/* dark mode styles */
	:global(body) {
		background-color: #ffff;
		color: #030D22;
		transition: background-color 0.3s
	}
	:global(body) a {
		transition: background-color 0.3s
	}
	:global(body.dark-mode) {
		background-color: #030D22;
		color: #ffff;
	}

	/* :global(body.dark-mode) a {
		color: #ffff;
		transition: background-color 0.3s
	} */

	.nav-link {
		color: #ff2592;
	}

</style>

<nav>
	<div class="nav-brand">
		<a class="brand nav-link" href=".">JT</a>
	</div>
	<div class="nav-links">
		<a class="nav-link" rel=prefetch href="blog">blog</a>
		<a class="nav-link" href="talks">talks</a>
		<a class="nav-link" href="uses">uses</a>
		<a class="nav-link" href="reading">reading</a>
		<!-- for the blog link, we're using rel=prefetch so that Sapper prefetches
		     the blog data when we hover over the link or tap it on a touchscreen -->
		<Button bind:isDarkMode={isDarkMode}>
			{#if isDarkMode}
				<SunIcon size="18" />
			{:else}
				<MoonIcon size="18"/>
			{/if}
		</Button>
	</div>
</nav>
