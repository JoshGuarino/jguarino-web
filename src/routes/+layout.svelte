<script lang="ts">
	import '../app.postcss';
	import { AppShell, AppBar, Avatar } from '@skeletonlabs/skeleton';
	import { LightSwitch } from '@skeletonlabs/skeleton';
	import Theme from '$lib/compoenents/theme.svelte';
	import Terminal from '$lib/compoenents/terminal.svelte';

	// Highlight JS
	import hljs from 'highlight.js/lib/core';
	import 'highlight.js/styles/github-dark.css';
	import { storeHighlightJs } from '@skeletonlabs/skeleton';
	import xml from 'highlight.js/lib/languages/xml'; // for HTML
	import css from 'highlight.js/lib/languages/css';
	import javascript from 'highlight.js/lib/languages/javascript';
	import typescript from 'highlight.js/lib/languages/typescript';

	hljs.registerLanguage('xml', xml); // for HTML
	hljs.registerLanguage('css', css);
	hljs.registerLanguage('javascript', javascript);
	hljs.registerLanguage('typescript', typescript);
	storeHighlightJs.set(hljs);

	// Floating UI for Popups
	import { computePosition, autoUpdate, flip, shift, offset, arrow } from '@floating-ui/dom';
	import { storePopup } from '@skeletonlabs/skeleton';
	storePopup.set({ computePosition, autoUpdate, flip, shift, offset, arrow });
</script>

<!-- App Shell -->
<AppShell>
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar>
			<svelte:fragment slot="lead">
				<strong class="text-xl uppercase"
					><Avatar initials="JG" background="variant-soft-primary" /></strong
				>
			</svelte:fragment>
			<svelte:fragment slot="trail">
				<div>
					<Terminal></Terminal>
				</div>
				<div>
					<Theme></Theme>
				</div>
				<div>
					<LightSwitch />
				</div>
				<a
					class="btn btn-sm variant-ghost-surface"
					href="https://www.linkedin.com/in/josh-guarino/"
					target="_blank"
					rel="noreferrer"
				>
					Linkedin
				</a>
				<a
					class="btn btn-sm variant-ghost-surface"
					href="https://github.com/joshguarino"
					target="_blank"
					rel="noreferrer"
				>
					GitHub
				</a>
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>
