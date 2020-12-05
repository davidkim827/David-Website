<script>
	import { getContext } from 'svelte';
	import { TABS } from './Tabs.svelte';

	const tab = {};
	const { registerTab, selectTab, selectedTab } = getContext(TABS);

	registerTab(tab);
</script>

<style>
	button {
		background: none;
		border: inherit;
		border-bottom: 2px solid white;
		border-radius: 0;
		margin: auto;
		color: #ccc;
		border-radius: 30px;
	}

	button:hover{
		background-color: #24a0ed;
        box-shadow: 0px 15px 20px rgba(0, 0, 0, 0.1);
        color: #fff;
	}
	
	.selected {
		background-color: #24a0ed;
		color: #fff;
		transition:all 5s;
	}
</style>

<button class:selected="{$selectedTab === tab}" on:click="{() => selectTab(tab)}">
	<slot></slot>
</button>