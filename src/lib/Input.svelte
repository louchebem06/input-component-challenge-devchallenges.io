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
	export let row: number = 1;
	const placeholder: string = "Placeholder"
	let focus: boolean = false;
</script>

<div
	class="container"
	class:fullWidth={fullWidth}
>
	<!-- svelte-ignore a11y-label-has-associated-control -->
	<label
		class:error={error}
		class:focus={focus}
	>Label</label>
	<div
		class="input"
		class:disabled={disabled}	
		class:error={error}
		class:focus={focus}
	>
		{#if startIcon}
			<span class="material-symbols-rounded">
				call
			</span>
		{/if}
		{#if !multiline}
			<input
				class:sm={size === "sm"}
				class:md={size === "md"}
				type="text"
				bind:value={value}
				{placeholder}
				{disabled}
				on:focus={() => {focus = true}}
				on:focusout={() => {focus = false}}
			/>
		{:else}
			<textarea
				rows={row}
				{disabled}
				{placeholder}
				on:focus={() => {focus = true}}
				on:focusout={() => {focus = false}}
			>{value}</textarea>
		{/if}
		{#if endIcon}
			<span class="material-symbols-rounded">
				lock
			</span>
		{/if}
	</div>
	<p
		class:error={error}
		class:focus={focus}
	>{helperText}</p>
</div>

<style>
	.container {
		display: flex;
		width: 200px;
		flex-direction: column;
		gap: 4px;
	}

	.fullWidth {
		width: 100%;
	}

	.input {
		display: flex;
		justify-content: space-between;
		border: 1px solid #828282;
		align-items: center;
		border-radius: 8px;
		padding: 12px;
	}

	.input:hover {
		border: 1px solid #333333;
	}

	.focus {
		color: #2962FF;
	}

	.input.focus {
		border: 1px solid #2962FF;
	}

	.error {
		color: #D32F2F!important;
	}

	.input.error {
		border: 1px solid #D32F2F!important;
	}

	input, textarea {
		width: 100%;
		border: none;
		background: transparent;
		outline: none;
	}

	.disabled {
		background: #F2F2F2;
		border: 1px solid #E0E0E0;
	}

	.sm {
		height: calc(40px - 24px);
	}

	.md {
		height: calc(56px - 24px);
	}

	textarea {
		resize: none;
	}

	.input span:nth-child(1) {
		padding-right: 15px;
	}

	.input span:nth-child(2) {
		padding-left: 15px;
	}

	label, p, input, textarea, ::placeholder {
		font-style: normal;
	}

	label, p {
		font-weight: 400;
	}

	input, textarea, ::placeholder {
		font-weight: 500;
		font-size: 14px;
		line-height: 20px;
	}

	label, input, textarea {
		color: #333333;
	}

	p, .input span {
		color: #828282;
	}

	label {	
		font-size: 12px;
		line-height: 17px;
	}

	p {
		font-size: 10px;
		line-height: 14px;
	}
</style>
