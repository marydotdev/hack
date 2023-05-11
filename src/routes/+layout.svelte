<script>
	import '../app.css';
	import ThemeToggle from '../lib/ThemeToggle.svelte';
</script>

<div class="w-full h-screen font-spacemono flex flex-col justify-between">
	<div>
		<nav class="z-10 sticky top-0 bg-zinc-50 dark:bg-zinc-900 border-b-2 border-zinc-900 dark:border-zinc-50">
			<div class="w-full p-4 flex items-center justify-between">
				<div class="w-fit">
					<a href="/" class="font-medium text-lg">hack.dev</a>
				</div>
				<div class="w-fit h-6">
					<ThemeToggle />
				</div>
			</div>
		</nav>
		<slot />
	</div>
	<footer class="z-10 sticky bottom-0 bg-zinc-50 dark:bg-zinc-900 border-t-2 border-zinc-900 dark:border-zinc-50">
		<div class="w-full p-4 flex items-center justify-center">made by mary</div>
	</footer>
</div>
