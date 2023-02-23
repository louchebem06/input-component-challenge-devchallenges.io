<script lang="ts">
	export let error: boolean = false;
	export let disabled: boolean = false;
	export let helperText: string = "";
	export let startIcon: boolean = false;
	export let endIcon: boolean = false;
	export let value: string = "";
	export let size: string = "md";
	export let fullWidth: boolean = false;
	export let multiline: boolean = false;
	export let row: number | string = "1";
	const placeholder: string = "Placeholder"
</script>

<span
	class:error={error}
	class:sm={() => {size == "sm"}}
	class:md={() => {size == "md"}}
	class:fullWidth={fullWidth}
>
	<!-- svelte-ignore a11y-label-has-associated-control -->
	<label>Label</label>
	{#if startIcon}
		<span class="material-symbols-rounded">
			call
		</span>
	{/if}
	{#if !multiline}
		<input type="text" bind:value={value} {placeholder} {disabled}/>
	{:else}
		<textarea rows="{row}" {disabled}></textarea>
	{/if}
	{#if endIcon}
		<span class="material-symbols-rounded">
			lock
		</span>
	{/if}
	<p>{helperText}</p>
</span>

<style>
</style>