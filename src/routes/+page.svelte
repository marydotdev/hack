<script lang="ts">
	import { onMount } from 'svelte';

	let date = new Date();
	let mounted = false;

	$: today = date.toLocaleDateString('en-US', {
		weekday: 'long',
		year: 'numeric',
		month: 'long',
		day: 'numeric'
	});

	$: time = date.toLocaleTimeString('en-US', {
		hour: 'numeric',
		minute: '2-digit',
		second: 'numeric'
	});
	$: hours = date.getHours();

	$: greeting = hours < 12 ? 'Morning' : hours <= 16 && hours >= 12 ? 'Afternoon' : 'Evening';

	onMount(() => {
		mounted = true;
		const interval = setInterval(() => {
			date = new Date();
		}, 1000);
		return () => {
			clearInterval(interval);
		};
	});
</script>

<div class="overflow-none flex h-full">
	<!-- <div class="hidden sm:flex flex-col gap-2 w-fit p-4">
		<a href="/">/home</a>
		<a href="/about">/about</a>
		<a href="/projects">/projects</a>
	</div> -->
	{#if mounted}
		<div class="w-full p-4">
			<div class="w-64">
				<h1 class="tracking-tighter text-lg sm:text-2xl font-medium">
					<span>Good {greeting},</span>
					<br />
					<span>Visitor.</span>
				</h1>

				<h2 class="pt-4 text-sm">
					{today}<br />{time}
				</h2>

				<div class="pt-8 w-full flex gap-4 text-sm sm:text-base">
					<a href="mailto:hello@mary.dev" target="_blank"> email </a>

					<a href="https://github.com/marydotdev" target="_blank"> github </a>

					<a href="https://twitter.com/marydotdev" target="_blank"> twitter </a>
				</div>
			</div>

			<div class="text-4xl pt-12 max-w-4xl">
				<p>
					Lorem ipsum dolor sit amet consectetur adipisicing elit. Sit dolores doloremque, quidem
					modi autem amet consectetur officiis eum a animi, quo rerum, magni eius similique quos
					obcaecati doloribus praesentium ut!
				</p>
				<p>
					Lorem ipsum dolor sit amet consectetur adipisicing elit. Sit dolores doloremque, quidem
					modi autem amet consectetur officiis eum a animi, quo rerum, magni eius similique quos
					obcaecati doloribus praesentium ut!
				</p>
			</div>
		</div>
	{/if}
</div>
