<script>
    const items = new Array(5000).fill('');
    let selectedItem = null;
</script>

{#if selectedItem}
    <strong>Last item selected: {selectedItem + 1}</strong>
{/if}
<section class="items-container">
    {#each items as _, index}
        <div class="item">
            <button disabled={selectedItem === index} on:click={() => selectedItem = index}>Item {index + 1}</button>
        </div>
    {/each}
</section>

<style>
    .items-container {
        display: flex;
        gap: 12px;
        flex-wrap: wrap;
    }

    .item {
        flex: 1;
    }
</style>
