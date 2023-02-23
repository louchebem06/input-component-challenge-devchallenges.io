<script lang="ts">
	import Input from "$lib/Input.svelte";
</script>

<svelte:head>
	<title>Input component challenge</title>
</svelte:head>

<Input />
<Input error />
<Input disabled />
<Input helperText="Some interesting text" />
<Input helperText="Some interesting text" error />
<Input startIcon />
<Input endIcon />
<Input value="text" />
<Input size="sm" />
<Input size="md" />
<Input fullWidth />
<Input multiline row="4" />
