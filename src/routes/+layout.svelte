<script>
	import '../app.css';
	import Navbar from '$components/Navbar.svelte';
</script>

<Navbar />
<div class="mt-6rem" style="background-color: #fff;">
	<slot />
</div>

<style>
	.mt-6rem {
		margin-top: 6rem;
	}
</style>
