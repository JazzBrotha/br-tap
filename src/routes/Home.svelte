<script>
    import { onMount } from "svelte";
    export let beers;
    onMount(async () => {
        await fetch(`http://localhost:5000/beer`)
            .then((r) => r.json())
            .then((data) => {
                console.log(data);
                beers = data;
            });
    });
</script>

{#if beers}
    <ul>
        {#each beers as beer}
            <li>
                <a href="/beer/{beer._id}">
                    {beer.name}
                </a>
            </li>
        {/each}
    </ul>
{/if}
