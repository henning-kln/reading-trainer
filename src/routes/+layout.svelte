<script lang="ts">
	import '../app.postcss';
	import { Toast, initializeStores } from '@skeletonlabs/skeleton';

	// Highlight JS
	import hljs from 'highlight.js/lib/core';
	import 'highlight.js/styles/github-dark.css';
	import { storeHighlightJs } from '@skeletonlabs/skeleton';
	import xml from 'highlight.js/lib/languages/xml'; // for HTML
	import css from 'highlight.js/lib/languages/css';
	import javascript from 'highlight.js/lib/languages/javascript';
	import typescript from 'highlight.js/lib/languages/typescript';
	initializeStores();
	hljs.registerLanguage('xml', xml); // for HTML
	hljs.registerLanguage('css', css);
	hljs.registerLanguage('javascript', javascript);
	hljs.registerLanguage('typescript', typescript);
	storeHighlightJs.set(hljs);

	// Floating UI for Popups
	import { computePosition, autoUpdate, flip, shift, offset, arrow } from '@floating-ui/dom';
	import { storePopup } from '@skeletonlabs/skeleton';
  	import Navbar from '$lib/Components/Navbar.svelte';
	storePopup.set({ computePosition, autoUpdate, flip, shift, offset, arrow });
</script>
<Toast/>
<div class="">
	<Navbar>
		<div class="flex h-full w-full items-center justify-center text-white">
			<div class="flex rounded-lg w-8/12 border min-h-96 bg-black/20 flex-col space-y-2 items-center p-2">
				<slot />
			</div>
		</div>
	</Navbar>
</div>


