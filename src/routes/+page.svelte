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

<svelte:head>
	<title>hack</title>
	<meta name="description" content="hack - a sveltekit template" />
</svelte:head>

<div
	class="h-[calc(100vh-120px)] lg:h-full overflow-none flex flex-col lg:flex-row lg:justify-between"
>
	{#if mounted}
		<div class="w-full lg:w-fit p-4 border-2 border-zinc-900 dark:border-zinc-50">
			<div class="w-64">
				<h1 class="tracking-tighter text-lg sm:text-2xl font-medium">
					<span>Good {greeting},</span>
					<br />
					<span>Visitor.</span>
				</h1>

				<h2 class="pt-4 text-sm">
					{today}<br />{time}
				</h2>
			</div>
		</div>
		<div
			class="scrollbar px-2 py-4 w-full lg:h-[calc(100vh-120px)] lg:overflow-y-scroll border-2 border-zinc-900 dark:border-zinc-50"
		>
			<div>
				<article class="mx-auto prose prose-zinc dark:prose-invert">
					<header id="title">
						<h1>AS WE MAY THINK</h1>
						<h2 class="-mt-8">by VANNEVAR BUSH</h2>
						<h3>THE ATLANTIC MONTHLY, JULY 1945</h3>
					</header>

					<blockquote>
						As Director of the Office of Scientific Research and Development, Dr. Vannevar Bush has
						coordinated the activities of some six thousand leading American scientists in the
						application of science to warfare. In this significant article he holds up an incentive
						for scientists when the fighting has ceased. He urges that men of science should then
						turn to the massive task of making more accessible our bewildering store of knowledge.
						For many years inventions have extended man's physical powers rather than the powers of
						his mind. Trip hammers that multiply the fists, microscopes that sharpen the eye, and
						engines of destruction and detection are new results, but the end results, of modern
						science. Now, says Dr. Bush, instruments are at hand which, if properly developed, will
						give man access to and command over the inherited knowledge of the ages. The perfection
						of these pacific instruments should be the first objective of our scientists as they
						emerge from their war work. Like Emerson's famous address of 1837 on ``The American
						Scholar,'' this paper by Dr. Bush calls for a new relationship between thinking man and
						the sum of our knowledge.
					</blockquote>
					<cite>- The Editor</cite>

					<main>
						<section id="0">
							<p>
								This has not been a scientist's war; it has been a war in which all have had a part.
								The scientists, burying their old professional competition in the demand of a common
								cause, have shared greatly and learned much. It has been exhilarating to work in
								effective partnership. Now, for many, this appears to be approaching an end. What
								are the scientists to do next?
							</p>

							<p>
								For the biologists, and particularly for the medical scientists, there can be little
								indecision, for their war has hardly required them to leave the old paths. Many
								indeed have been able to carry on their war research in their familiar peacetime
								laboratories. Their objectives remain much the same.
							</p>

							<p>
								It is the physicists who have been thrown most violently off stride, who have left
								academic pursuits for the making of strange destructive gadgets, who have had to
								devise new methods for their unanticipated assignments. They have done their part on
								the devices that made it possible to turn back the enemy, have worked in combined
								effort with the physicists of our allies. They have felt within themselves the stir
								of achievement. They have been part of a great team. Now, as peace approaches, one
								asks where they will find objectives worthy of their best.
							</p>
						</section>
						<section id="1">
							<h4>I</h4>

							<p>
								Of what lasting benefit has been man's use of science and of the new instruments
								which his research brought into existence? First, they have increased his control of
								his material environment. They have improved his food, his clothing, his shelter;
								they have increased his security and released him partly from the bondage of bare
								existence. They have given him increased knowledge of his own biological processes
								so that he has had a progressive freedom from disease and an increased span of life.
								They are illuminating the interactions of his physiological and psychological
								functions, giving the promise of an improved mental health.
							</p>

							<p>
								Science has provided the swiftest communication between individuals; it has provided
								a record of ideas and has enabled man to manipulate and to make extracts from that
								record so that knowledge evolves and endures throughout the life of a race rather
								than that of an individual.
							</p>

							<p>
								There is a growing mountain of research. But there is increased evidence that we are
								being bogged down today as specialization extends. The investigator is staggered by
								the findings and conclusions of thousands of other workers - conclusions which he
								cannot find time to grasp, much less to remember, as they appear. Yet specialization
								becomes increasingly necessary for progress, and the effort to bridge between
								disciplines is correspondingly superficial.
							</p>

							<p>
								Professionally our methods of transmitting and reviewing the results of research are
								generations old and by now are totally inadequate for their purpose. If the
								aggregate time spent in writing scholarly works and in reading them could be
								evaluated, the ratio between these amounts of time might well be startling. Those
								who conscientiously attempt to keep abreast of current thought, even in restricted
								fields, by close and continuous reading might well shy away from an examination
								calculated to show how much of the previous month's efforts could be produced on
								call. Mendel's concept of the laws of genetics was lost to the world for a
								generation because his publication did not reach the few who were capable of
								grasping and extending it; and this sort of catastrophe is undoubtedly being
								repeated all about us, as truly significant attainments become lost in the mass of
								the inconsequential.
							</p>

							<p>
								The difficulty seems to be, not so much that we publish unduly in view of the extent
								and variety of present-day interests, but rather that publication has been extended
								far beyond our present ability to make real use of the record. The summation of
								human experience us being expanded at a prodigious rate, and the means we use for
								threading through the consequent maze to the momentarily important item is the same
								as was used in the days of square-rigged ships.
							</p>

							<p>
								But there are signs of a change as new and powerful instrumentalities come into use.
								Photocells capable of seeing things in a physical sense, advanced photography which
								can record what is seen or even what is not, thermionic tubes capable of controlling
								potent forces under the guidance of less power than a mosquito uses to vibrate his
								wings, cathode ray tubes rendering visible an occurrence so brief that by comparison
								a microsecond is a long time, relay combinations which will carry out involved
								sequences of movements more reliably than any human operator and thousand of times
								as fast - there are plenty of mechanical aids with which to effect a transformation
								in scientific records.
							</p>

							<p>
								Two centuries ago Leibnitz invented a calculating machine which embodied most of the
								essential features of recent keyboard devices, but it could not then come into use.
								The economics of the situation were against it: the labor involved in constructing
								it, before the days of mass production, exceeded the labor to be saved by its use,
								since all it could accomplish could be duplicated by sufficient use of pencil and
								paper. Moreover, it would have been subject to frequent breakdown, so that it could
								not have been depended upon; for at that time and long after, complexity and
								unreliability were synonymous.
							</p>

							<p>
								Babbage, even with remarkably generous support for his time, could not produce his
								great arithmetical machine. His idea was sound enough, but construction and
								maintenance costs were then too heavy. Had a Pharaoh been given detailed and
								explicit designs of an automobile, and had he understood them completely, it would
								have taxed the resources of his kingdom to have fashioned the thousands of parts for
								a single car, and that car would have broken down on the first trip to Giza.
							</p>

							<p>
								Machines with interchangeable parts can now be constructed with great economy of
								effort. In spite of much complexity, they perform reliably. Witness the humble
								typewriter, or the movie camera, or the automobile. Electrical contacts have ceased
								to stick when thoroughly understood. Note the automatic telephone exchange, which
								has hundred of thousands of such contacts, and yet is reliable. A spider web of
								metal, sealed in a thin glass container, a wire heated to brilliant glow, in short,
								the thermionic tube of radio sets, is made by the hundred million, tossed about in
								packages, plugged into sockets - and it works! Its gossamer parts, the precise
								location and alignment involved in its construction, would have occupied a master
								craftsman of the guild for months; now it is built for thirty cents. The world has
								arrived at an age of cheap complex devices of great reliability; and something is
								bound to come of it.
							</p>
						</section>
					</main>

          <a href="/as-we-may-think" class="block ml-auto mr-0 w-fit">Read More &rarr;</a>
				</article>
			</div>
		</div>
		<div class="w-full lg:w-fit p-4 border-2 border-zinc-900 dark:border-zinc-50">
			<div class="w-64">
				<div class="w-full flex flex-col gap-4 text-sm sm:text-base">
					<a href="#title">/</a>

					<a href="#1">/I</a>

					<a href="/as-we-may-think">/as-we-may-think</a>
				</div>
			</div>
		</div>
	{:else}
		<div class="h-full">
			<p>loading</p>
		</div>
	{/if}
</div>
