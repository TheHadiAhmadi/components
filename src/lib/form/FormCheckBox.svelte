<script lang="ts">
	import { CheckboxGroup } from 'yesvelte';
	import FormField from './FormField.svelte';

	export let name: string;
	export let value: any[] = [];
	export let items: any[] = [];

	function set(val: any) {
		value = val;
	}

	function get() {
		return value;
	}

	function onChange(e: any) {
		value = e.target.value;
	}
</script>

<FormField {name} {get} {set} bind:value>
	<CheckboxGroup {...$$props} {name} {items} bind:value inline on:change={onChange} />
</FormField>
