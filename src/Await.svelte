<script>
	export let name;

	const waitOneSec = () =>
		new Promise(resolve => setTimeout(() => resolve(true), 1000));
	const asyncCall = async () => await waitOneSec();

	const data = asyncCall();
</script>

{#await data}
	<p>Awaiting...</p>
{:then data}
	<h1>Hello {name}!</h1>
{:catch error}
	<p>Error</p>
{/await}
