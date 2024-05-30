<script>
	import { PUBLIC_CLOUDFLARE_URL } from '$env/static/public';

	export let details;
	export let price;
	export let title;
	export let imageSrc;

	let showDetails = false;
	const fullImgURL = `${PUBLIC_CLOUDFLARE_URL}/${imageSrc}`;
</script>

<div id="container">
	<div id="title">{title}</div>
	<img src={fullImgURL} alt={title} />
	<div>${price.toFixed(2)}</div>
	<button id="show-details-button" on:click={() => (showDetails = !showDetails)}>
		{showDetails ? 'hide' : 'show'} details
	</button>
	{#if showDetails}
		<div id="details">{details}</div>
	{/if}
</div>

<style>
	#title {
		font-size: 1.2rem;
	}

	#show-details-button {
		border: none;
		background-color: inherit;
		padding: 0.5rem 0;
		text-decoration: underline;
		cursor: pointer;
	}

	#details {
		font-style: italic;
	}

	#container {
		width: 200px;
	}

	img {
		width: 200px;
		height: 200px;
		object-fit: cover;
	}
</style>
