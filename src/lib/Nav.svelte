<script>
  import ThemeToggle from '$lib/ThemeToggle.svelte';
</script>

<nav class="z-10 bg-zinc-50 dark:bg-zinc-900 border-b-2 border-zinc-900 dark:border-zinc-50">
	<div class="w-full p-4 flex items-center justify-between">
		<div class="w-fit">
			<a href="/" class="font-medium text-lg">hack</a>
		</div>
		<div class="w-fit h-6">
			<ThemeToggle />
		</div>
	</div>
</nav>
