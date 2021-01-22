<script>
    import { onMount } from "svelte";
    export let location, beer;
    onMount(async () => {
        await fetch(`http://localhost:5000${location.pathname}`)
            .then((r) => r.json())
            .then((data) => {
                console.log(data);
                beer = data;
            });
    });
</script>

{#if beer}
    <ul>
        {#each beer as beer}
            <li>
                <a href="/beer/{beer._id}">
                    {beer.name}
                </a>
            </li>
        {/each}
    </ul>
{/if}
