<script lang="ts">
	import sourceengine from '$lib/assets/img/halflife.jpg';
	import mindus from '$lib/assets/img/mindustry.webp';
	import mc from '$lib/assets/img/minecraft.jfif';
	import logo from '$lib/assets/img/apple-touch-icon.png';
	import { onMount } from 'svelte';
	let Carousel;
	onMount(async () => {
		const module = await import('svelte-carousel');
		Carousel = module.default;
	});
	const items = [
		{
			name: 'Sultan Bismillah II',
			review:
				'Cheapest hosting ever. Very nice support and helped me all the way through my setup!',
			role: 'Customer',
			image: '/img/testimonials/testimonials-0.gif'
		},
		{
			name: 'RT Omega',
			review:
				'Yeet Hosting is just amazing, it has great ping and its better than what i was previously using.',
			role: 'Omega Hub Owner',
			image: '/img/testimonials/testimonials-1.jpg'
		},
		{
			name: 'Schutz',
			review: 'Simple, Fast, Good Support',
			role: 'Customer',
			image: '/img/testimonials/testimonials-2.jpg'
		},
		{
			name: 'KingBR',
			review:
				'Cheap, stable, highly customizable options and fast support. You can use it for either small servers with your friends or servers for dozens of people.',
			role: 'Owner of MindustryBR',
			image: '/img/testimonials/testimonials-3.png'
		},
		{
			name: 'TheRadioactiveBanana',
			review:
				'Amazing hosting service with highly customisable server interface that is easy to use too. servers are fast and start quickly. ',
			role: 'Owner of Eradication Mindustry',
			image: '/img/testimonials/testimonials-4.png'
		}
	];
</script>

<div class="card bg-base-100 shadow-xl transition-shadow">
	<div class="card-body text-center">
		<h1 class="text-center text-4xl font-extrabold sm:text-4xl md:text-4xl">
			Secure, flexible, reliable
		</h1>
		<h1
			class="
			m-2 bg-gradient-to-l from-yellow-500 via-green-500
			to-cyan-500 bg-clip-text p-1
			text-center text-4xl font-extrabold
			text-transparent sm:h-28 sm:text-4xl md:text-8xl
			"
		>
			Yeet Hosting.
		</h1>
		<div
			class="m-2
		 flex flex-wrap
		  justify-center p-1
		  sm:justify-evenly md:justify-between
		  "
		>
			<div class="card m-2 border-2 border-red-500 bg-base-100 shadow-xl sm:w-48 md:w-72">
				<div class="card-body">
					<h2 class="card-title">
						<svg
							xmlns="http://www.w3.org/2000/svg"
							fill="none"
							viewBox="0 0 24 24"
							stroke-width="1.5"
							stroke="currentColor"
							class="h-6 w-6 stroke-red-500"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								d="M7.5 8.25h9m-9 3H12m-9.75 1.51c0 1.6 1.123 2.994 2.707 3.227 1.129.166 2.27.293 3.423.379.35.026.67.21.865.501L12 21l2.755-4.133a1.14 1.14 0 01.865-.501 48.172 48.172 0 003.423-.379c1.584-.233 2.707-1.626 2.707-3.228V6.741c0-1.602-1.123-2.995-2.707-3.228A48.394 48.394 0 0012 3c-2.392 0-4.744.175-7.043.513C3.373 3.746 2.25 5.14 2.25 6.741v6.018z"
							/>
						</svg>
						24/7 Support
					</h2>
				</div>
			</div>
			<div class="card m-2 border-2 border-blue-500 bg-base-100 shadow-xl sm:w-48 md:w-72">
				<div class="card-body">
					<h2 class="card-title">
						<svg
							xmlns="http://www.w3.org/2000/svg"
							fill="none"
							viewBox="0 0 24 24"
							stroke-width="1.5"
							stroke="currentColor"
							class="h-6 w-6 stroke-blue-500"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								d="M16.023 9.348h4.992v-.001M2.985 19.644v-4.992m0 0h4.992m-4.993 0l3.181 3.183a8.25 8.25 0 0013.803-3.7M4.031 9.865a8.25 8.25 0 0113.803-3.7l3.181 3.182m0-4.991v4.99"
							/>
						</svg>
						Low Ping
					</h2>
				</div>
			</div>
			<div class="card m-2 border-2 border-white bg-base-100 shadow-xl sm:w-48 md:w-72">
				<div class="card-body">
					<h2 class="card-title">
						<svg
							xmlns="http://www.w3.org/2000/svg"
							fill="none"
							viewBox="0 0 24 24"
							stroke-width="1.5"
							stroke="currentColor"
							class="h-6 w-6"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								d="M3.75 13.5l10.5-11.25L12 10.5h8.25L9.75 21.75 12 13.5H3.75z"
							/>
						</svg>
						99.997% Uptime
					</h2>
				</div>
			</div>
		</div>
		<svelte:component
			this={Carousel}
			let:showPrevPage
			let:showNextPage
			autoplay
			autoplayDuration={3000}
		>
			<button type="button" slot="prev" on:click={showPrevPage} />
			{#each items as item, i (item.name)}
				<div style="padding: 30px 8px; text-align: center; background: #; border-radius: 5px;">
					<div class="flex w-full flex-col items-center justify-center">
						<h1 class="w-4/5 text-center text-2xl leading-relaxed transition-all">
							"{item.review}"
						</h1>
						<div class="flex h-20 items-center gap-5">
							<div class="h-12 w-12 overflow-hidden rounded-full bg-black">
								<img alt="testimonial" src={item.image} />
							</div>
							<div class="flex flex-col tracking-wider">
								<!-- svelte-ignore a11y-label-has-associated-control -->
								<label class=" text-base font-bold">{item.name}</label>
								<!-- svelte-ignore a11y-label-has-associated-control -->
								<label class="text-sm font-normal text-gray-400">{item.role}</label>
							</div>
						</div>
					</div>
				</div>
			{/each}
			<button type="button" slot="next" on:click={showNextPage} />
		</svelte:component>
		<div class="card-body" />
	</div>
</div>
<div id="services" class="card bg-base-100 shadow-xl lg:card-side">
	<div class="card-body">
		<h1 class="card-title flex flex-wrap justify-center text-3xl font-bold">Services</h1>
		<div class="divider" />
		<div class="flex flex-row flex-wrap sm:justify-evenly md:justify-between">
			<!-- Mindustry Card -->
			<div class="card image-full m-2 w-72 bg-base-100 shadow-xl hover:bg-base-300">
				<figure>
					<img src={mindus} width="400" height="225" alt="Mindustry" />
				</figure>
				<div class="card-body">
					<h2 class="card-title">Mindustry Hosting</h2>
					<div class="divider" />
					<p>
						We are experts in doing this service, just ask us to set your server up after buying,
						its free.
					</p>
					<h2 class="card-title text-2xl">Starting From $3/m</h2>
				</div>
			</div>
			<br />
			<!-- Minecraft Card -->
			<div class="card image-full m-2 w-72 bg-base-100 shadow-xl hover:bg-base-300">
				<figure>
					<img src={mc} alt="Minecraft" />
				</figure>
				<div class="card-body">
					<h2 class="card-title">Minecraft Hosting</h2>
					<div class="badge-secondary badge">NEW</div>
					<div class="divider" />
					<p>We provide you with utilities and DDOS protection to ensure your server's uptime!</p>
					<h2 class="card-title text-2xl">Starting From $6/m</h2>
				</div>
			</div>
			<br />
			<!-- Source Engine Card -->
			<div class="card image-full m-2 w-72 bg-base-100 shadow-xl hover:bg-base-300">
				<figure>
					<img src={sourceengine} width="400" height="255" alt="Source Engine" />
				</figure>
				<div class="card-body">
					<h2 class="card-title">SteamCMD Hosting</h2>
					<div class="divider" />
					<p>You can create a server on your favorite steam games!</p>
					<h2 class="card-title text-2xl">Starting from 12$/m</h2>
				</div>
			</div>
			<br />
			<!-- ETC -->
			<div class="card image-full m-2 w-72 bg-base-100 shadow-xl hover:bg-base-300">
				<figure><img src={logo} width="400" height="255" alt="ETC" /></figure>
				<div class="card-body">
					<h2 class="card-title">Discord Bot, Database, Voice Server Hosting</h2>
					<div class="badge-secondary badge">NEW</div>
					<div class="divider" />
					<p>For developers, we also offer a cheap plan to get started.</p>
					<h2 class="card-title text-2xl">Starting From 0.50$/m</h2>
				</div>
			</div>
			<br />
		</div>
	</div>
</div>
<div class="hero h-80 bg-base-100">
	<div class="hero-content text-center">
		<div class="max-w-md">
			<h1 class="text-5xl font-bold">What are you waiting for?</h1>
			<p class="py-7" />
			<a href="/pricing/" class="btn-secondary btn">Get Started</a>
		</div>
	</div>
</div>
