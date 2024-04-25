<script>
    import { menu_items } from '$lib/menu_items.js'
    import { base } from '$app/paths';

    import { getDrawerStore } from '@skeletonlabs/skeleton';

    const drawerStore = getDrawerStore();

    function closeDrawer() {
        drawerStore.close();
    }
</script>
<nav class="list-nav p-4">
    <ul>
        {#each Object.entries(menu_items) as [key, item]}
        <li><a
            on:click={closeDrawer}
            href="{base}{key}">
            {item}
        </a></li>
        {/each}
        <!-- <li><a href="/">Home</a></li>
        <li><a href="/about">About</a></li>
        <li><a href="/contact">Contact</a></li> -->
    </ul>
</nav>