<script lang="ts">
	import Description from '$lib/components/core/description.svelte';
	import Units from '$lib/components/core/units.svelte';
	import { colorsMap, writings, type units } from '$lib/utils/consts';
	import { onMount } from 'svelte';
	let description = `
Embark on a journey through the dynamic landscape of web development, cyber security, and machine learning with a focus on React and Svelte. As an Indie creator, I share insights into crafting seamless user interfaces, securing digital landscapes, and applying machine learning in real-world scenarios`;

	onMount(() => {
		document.documentElement.style.setProperty('--primary', colorsMap.get('writings'));
	});
</script>

<div class="writings">
	<Description header="My writings" {description} />
	<Units units={writings} />
</div>

<style>
	.writings {
		width: 80%;
		display: flex;
		flex-direction: column;
		padding-left: 5%;
		gap: 40px;
	}

	@media screen and (width < 768px) {
		.writings {
			width: 95%;
		}
	}
</style>
