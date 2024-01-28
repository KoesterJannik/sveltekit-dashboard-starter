<script>
	import Navbar from '../../components/Navbar.svelte';
</script>

<div class="flex h-screen flex-col overflow-hidden">
	<Navbar />
	<div class="overflow-hidden">
		<slot />
	</div>
</div>
