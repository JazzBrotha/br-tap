<script>
    import { onMount } from 'svelte'
    let beer
    onMount(async () => {
        const beerResponse = await fetch(
            `http://localhost:3000/beer/594111ecffe15a2652471936`
        )
        beer = await beerResponse.json()
    })
</script>

<p>{beer && beer.name}</p>
