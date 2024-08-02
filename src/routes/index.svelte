<script context="module">
    import { products, getProducts } from '../../store';
    export async function load(ctx) {
        await getProducts();
        return { props: { products } };
    }
</script>

<script>
export let products;
</script>
<svelte:head>
    <title>Home</title>
</svelte:head>
<section>
<h2>
    {#each $products as product}
        <p>{product.node.title} </p>
    {/each}
</h2>
</section>