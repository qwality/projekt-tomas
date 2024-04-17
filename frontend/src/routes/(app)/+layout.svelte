<script>
    import { AppShell, AppBar, Avatar, Drawer, initializeStores, getDrawerStore } from '@skeletonlabs/skeleton';

    initializeStores();
    const drawerStore = getDrawerStore();

    import Navigation from '../../lib/compontnts/Navigation.svelte';
    import HamburgerIcon from "$lib/img/icon/common/hamburger.svg?component";
    import { constants } from "$lib/constants"

    function toggleDrawer() {
        drawerStore.open();
    }
</script>

<Drawer>
    <Navigation/>
</Drawer>

<AppShell slotSidebarLeft="w-0 md:w-52 bg-surface-500/10">
	<svelte:fragment slot="header">
        <AppBar>
            <svelte:fragment slot="lead">
                <!--   -->
                <button class="md:hidden btn btn-sm mr-4" on:click={toggleDrawer}>
                    <HamburgerIcon class="inline-block w-6 h-6 stroke-current" />
                </button>
                
            </svelte:fragment>
            {constants.app_name}
            <svelte:fragment slot="trail">
                <Avatar initials="{constants.app_name_initials}" width="w-10" background="bg-primary-500" />
            </svelte:fragment>
        </AppBar>
    </svelte:fragment>
	<svelte:fragment slot="sidebarLeft">
        <Navigation/>
    </svelte:fragment>
	<!-- (sidebarRight) -->
	<!-- (pageHeader) -->
	<!-- Router Slot -->
	<slot />
	<!-- ---- / ---- -->
	<svelte:fragment slot="pageFooter">
        <a href="https://www.skeleton.dev/">dokumentace</a>
    </svelte:fragment>
	<!-- (footer) -->
</AppShell>