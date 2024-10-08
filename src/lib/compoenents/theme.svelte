<script lang="ts">
	import { theme } from '$lib/stores/theme.js';
	import { popup, type PopupSettings } from '@skeletonlabs/skeleton';

	let themes = [
		['skeleton', "💀"], 
		['wintry', "🌨️"], 
		['modern', "🤖"], 
		['rocket', "🚀"], 
		['seafoam', "🧜‍♀️"], 
		['vintage', "📺"], 
		['sahara', "🏜️"], 
		['hamlindigo', "👔"], 
		['gold-nouveau', "💫"], 
		['crimson', "⭕"],
	]

	const popupTheme: PopupSettings = {
		event: 'click',
		target: 'popupTheme',
		placement: 'bottom'
	};

	function setThemeStore(value: string) {
		theme.set(value)
	}

	function setTheme(theme: string) {
		let currentThemeElement = document.getElementById($theme)
		let newThemeElement = document.getElementById(theme)
		currentThemeElement?.classList.remove('bg-primary-active-token')
		newThemeElement?.classList.add('bg-primary-active-token')
		document.body.setAttribute('data-theme', theme);
		setThemeStore(theme)
	}
</script>

<div>
	<button type="button" class="btn hover:variant-soft-primary" use:popup={popupTheme}>
		<span>Theme</span>
	</button>
</div>

<div class="card p-4 w-72 shadow-xl" data-popup="popupTheme">
	<nav class="list-nav p-4 -m-4 max-h-64 lg:max-h-[500px] overflow-y-auto">
		<ul>
			{#each themes as theme}
				<li>
					<button class="option w-full h-full" type="button" name="theme" id="wintry" on:click={() => setTheme(theme[0])}>
						<span>
							{theme[1]}
						</span>
						<span class="flex-auto text-left">
							{theme[0][0].toUpperCase() + theme[0].slice(1)}
						</span>
					</button>
				</li>
			{/each}
		</ul>
	</nav>
</div>
