<script>
	import FirstProjectSVG from '@components/FirstProjectSVG.svelte'
	import SecondProject from '@components/SecondProjectSVG.svelte'
	import gsap from 'gsap'
	import { onMount } from 'svelte'

	let tl
	let bg
	let header
	let image
	let p

	onMount(() => {
		const screenWidth = window.innerWidth
		tl = gsap.timeline()

		if (screenWidth >= 640) {
			tl.fromTo(bg, { x: '-100%' }, { x: 0, duration: 0.7 })
			tl.fromTo(header, { x: '-20%', opacity: 0 }, { x: 0, opacity: '100%', duration: 0.5 })
			tl.fromTo(image, { x: '-20%', opacity: 0 }, { x: 0, opacity: '100%', duration: 0.5 })
			tl.fromTo(p, { x: '-20%', opacity: 0 }, { x: 0, opacity: '100%', duration: 0.5 })
		}
	})
</script>

<section class="bg-zinc-200 xl:h-screen xl:w-screen xl:bg-transparent">
	<div bind:this={bg} class="absolute -z-10 hidden h-full w-full bg-zinc-200 xl:block"></div>
	<article class="mx-auto flex h-full w-10/12 flex-col py-20">
		<h1
			bind:this={header}
			class="mb-10 text-center font-serif text-5xl xl:mb-0 xl:mr-20 xl:self-end xl:text-[100px]"
		>
			L.A. Yachting
		</h1>
		<div class="items-center justify-center xl:flex xl:flex-row">
			<a
				bind:this={image}
				class="mx-auto my-10 mb-10 mr-auto w-[50rem]"
				href="https://la-yachting.com"
			>
				<img
					class="mb-10 rounded-2xl object-cover transition hover:scale-105 xl:mb-0"
					src="/yachting.png"
					alt="Screenshot L.A. Yachting"
				/>
			</a>
			<FirstProjectSVG />
		</div>
		<p bind:this={p} class="mx-auto max-w-prose bg-zinc-300 p-6 text-2xl">
			Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ad, alias amet assumenda autem
			debitis eligendi est eum exercitationem harum hic ipsum, iusto labore magnam natus quia quis
			rem sed, tempora. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dignissimos
			maiores porro possimus quae tempore? Asperiores at et eveniet laudantium minus omnis optio
			quam reiciendis similique, tempore ullam veritatis. Rerum, soluta!
		</p>
	</article>
</section>
<section class="xl:h-screen xl:w-screen">
	<div class="absolute -z-10 h-full w-full bg-zinc-100"></div>
	<article class="mx-auto flex h-full w-10/12 flex-col py-20">
		<h1
			class="mb-10 text-center text-5xl font-semibold xl:mb-0 xl:mr-40 xl:self-end xl:text-[100px]"
		>
			BookFreak
		</h1>
		<div class="items-center justify-center xl:flex xl:flex-row">
			<a class="mx-auto my-10 mr-auto w-[50rem] xl:mx-0" href="https://bookfreak.vercel.app/">
				<img
					class="mb-10 rounded-2xl object-cover transition hover:scale-105 xl:mb-0"
					src="/BookFreak.png"
					alt="Screenshot L.A. Yachting"
				/>
			</a>
			<SecondProject />
		</div>
		<p class="mx-auto max-w-prose bg-zinc-200 p-6 text-2xl">
			Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ad, alias amet assumenda autem
			debitis eligendi est eum exercitationem harum hic ipsum, iusto labore magnam natus quia quis
			rem sed, tempora. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dignissimos
			maiores porro possimus quae tempore? Asperiores at et eveniet laudantium minus omnis optio
			quam reiciendis similique, tempore ullam veritatis. Rerum, soluta!
		</p>
	</article>
</section>
