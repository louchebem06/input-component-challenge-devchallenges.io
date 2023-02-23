<script lang="ts">
	import Input from "$lib/Input.svelte";
  import Signature from "$lib/Signature.svelte";
</script>

<svelte:head>
	<title>Input component challenge</title>
</svelte:head>

<div class="content">
	<div class="element">
		<p>{"<Input />"}</p>
		<Input />
	</div>
	<div class="element">
		<p>{"<Input error />"}</p>
		<Input error />
	</div>
	<div class="element">
		<p>{"<Input disabled />"}</p>
		<Input disabled />
	</div>
	<div class="elements">
		<div class="element">
			<p>{"<Input helperText=\"Some interesting text\" />"}</p>
			<Input helperText="Some interesting text" />
		</div>
		<div class="element">
			<p>{"<Input helperText=\"Some interesting text\" error />"}</p>
			<Input helperText="Some interesting text" error />
		</div>
	</div>
	<div class="elements">
		<div class="element">
			<p>{"<Input startIcon />"}</p>
			<Input startIcon />
		</div>
		<div class="element">
			<p>{"<Input endIcon />"}</p>
			<Input endIcon />
		</div>
	</div>
	<div class="element">
		<p>{"<Input value=\"text\" />"}</p>
		<Input value="text" />
	</div>
	<div class="elements">
		<div class="element">
			<p>{"<Input size=\"sm\" />"}</p>
			<Input size="sm" />
		</div>
		<div class="element">
			<p>{"<Input size=\"md\" />"}</p>
			<Input size="md" />
		</div>
	</div>
	<div class="element">
		<p>{"<Input fullWidth />"}</p>
		<Input fullWidth />
	</div>
	<div class="element">
		<p>{"<Input multiline row=\"4\" />"}</p>
		<Input multiline row="4" />
	</div>
</div>

<Signature />

<style>
	.content {
		width: 90%;
		margin: 20px auto;
		display: flex;
		flex-direction: column;
		gap: 42px
	}

	.element {
		font-style: normal;
		font-weight: 400;
		font-size: 12px;
		line-height: 12px;
		color: #333333;
		display: flex;
		flex-direction: column;
		gap: 16px;
		min-width: 300px;
	}

	.elements {
		display: flex;
		gap: 69px;
	}
</style>
