<script lang="ts">
	import { i18n } from '$lib/i18n';
	import { ParaglideJS } from '@inlang/paraglide-sveltekit';
	import '../app.css';
	import '$lib/styles/fonts.css';
	import { Header } from '$lib/components/client/header';
	import { Footer } from '$lib/components/client/footer';

	let { children } = $props();
</script>

<ParaglideJS {i18n}>
	<div class="bg-background flex min-h-screen flex-col font-sans antialiased">
		<Header />
		<main class="flex-1 pt-16">
			<div class="mx-auto w-full px-4 py-8">
				<div class="main-layout">
					{@render children()}
				</div>
			</div>
		</main>
		<Footer />
	</div>
</ParaglideJS>

<style>
	.main-layout {
		font-family:
			'Inter',
			system-ui,
			-apple-system,
			BlinkMacSystemFont,
			sans-serif;
	}
</style>
