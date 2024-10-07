<script lang="ts">
	import { theme } from '$lib/stores/theme.js';
	import { popup, type PopupSettings } from '@skeletonlabs/skeleton';

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
		<!-- <span>💀</span> <span class="flex-auto text-left">Skeleton</span> -->
		<!-- <span>{$theme}</span> -->
	</button>
</div>

<div class="card p-4 w-72 shadow-xl" data-popup="popupTheme">
	<nav class="list-nav p-4 -m-4 max-h-64 lg:max-h-[500px] overflow-y-auto">
		<ul>
			<li>
				<button class="option w-full h-full bg-primary-active-token" type="button" name="theme" id="skeleton" on:click={() => setTheme("skeleton")}>
                    <span>💀</span> <span class="flex-auto text-left">Skeleton</span>
                </button>
			</li>
			<li>
				<button class="option w-full h-full" type="button" name="theme" id="wintry" on:click={() => setTheme("wintry")}>
                    <span>🌨️</span> <span class="flex-auto text-left">Wintry</span>
                </button>
			</li>
			<li>
				<button class="option w-full h-full" type="button" name="theme" id="modern" on:click={() => setTheme("modern")}>
                    <span>🤖</span> <span class="flex-auto text-left">Modern</span>
                </button>
			</li>
			<li>
				<button class="option w-full h-full" type="button" name="theme" id="rocket" on:click={() => setTheme("rocket")}>
                    <span>🚀</span> <span class="flex-auto text-left">Rocket</span>
                </button>
			</li>
			<li>
				<button class="option w-full h-full" type="button" name="theme" id="seafoam" on:click={() => setTheme("seafoam")}>
                    <span>🧜‍♀️</span> <span class="flex-auto text-left">Seafoam</span>
                </button>
			</li>
			<li>
				<button class="option w-full h-full" type="button" name="theme" id="vintage" on:click={() => setTheme("vintage")}>
                    <span>📺</span> <span class="flex-auto text-left">Vintage</span>
                </button>
			</li>
			<li>
				<button class="option w-full h-full" type="button" name="theme" id="sahara" on:click={() => setTheme("sahara")}>
                    <span>🏜️</span> <span class="flex-auto text-left">Sahara</span>
                </button>
			</li>
			<li>
				<button class="option w-full h-full" type="button" name="theme" id="hamlindigo" on:click={() => setTheme("hamlindigo")}>
                    <span>👔</span> <span class="flex-auto text-left">Hamlindigo</span>
                </button>
			</li>
			<li>
				<button class="option w-full h-full" type="button" name="theme" id="gold-nouveau" on:click={() => setTheme("gold-nouveau")}>
                    <span>💫</span> <span class="flex-auto text-left">Gold Nouveau</span>
                </button>
			</li>
			<li>
				<button class="option w-full h-full" type="button" name="theme" id="crimson" on:click={() => setTheme("crimson")}>
                    <span>⭕</span> <span class="flex-auto text-left">Crimson</span>
                </button>
			</li>
		</ul>
	</nav>
</div>
