<script>
	import { PUBLIC_CLOUDFLARE_URL } from '$env/static/public';

	export let src;
	export let alt;

	const fullURL = `${PUBLIC_CLOUDFLARE_URL}/${src}`;
</script>

<img src={fullURL} {alt} />

<style>
	img {
		width: 100%;
	}
</style>
