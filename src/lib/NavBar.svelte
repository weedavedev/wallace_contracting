<!-- src/routes/Navbar.svelte -->
<script>
    import {base} from '$app/paths';
    import {afterUpdate} from "svelte";
    import {goto} from '$app/navigation';

    afterUpdate(() => {
        console.log("Base path is:", base);
    }); // For debugging

    let isOpen = false; // Controls whether the mobile menu is open

    let hover = false;
    let show = true;
    let group = 'navGroup';
</script>

<nav class="menu-bg p-4 relative">
    <div class="flex justify-between items-center">
        <a href="/" class="logo">Logo</a>
        <button
                class="menu-toggle"
                on:click={() => isOpen = !isOpen}
                aria-label="Toggle menu"
        >
            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"
                 xmlns="http://www.w3.org/2000/svg">
                {#if isOpen}
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                          d="M6 18L18 6M6 6l12 12"></path>
                {:else}
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                          d="M4 6h16M4 12h16m-7 6h7"></path>
                {/if}
            </svg>
        </button>
    </div>

    <ul class={`md:flex md:space-x-4 mt-4 md:mt-0 ${isOpen ? 'block' : 'hidden'} absolute md:static menu-bg w-full`}>
        <li><a href="/home" on:click|preventDefault={() => goto('/home')} class="menu-link">HOME</a></li>
        <li class="relative group">
            <a href="/fencing" class="menu-link">FENCING</a>
            <ul class={`dropdown ${group-hover-show}`}>
                <li>
                    <a href="/fencing#stock" on:click|preventDefault={() => goto('/fencing/#stock')} class="menu-link">Stock
                        Fence</a>
                </li>
                <li>
                    <a href="/fencing#deer" on:click|preventDefault={() => goto('/fencing/#deer')} class="menu-link">Deer
                        Fence</a>
                </li>
            </ul>
        </li>

        <li class="relative group">
            <a href="/site_clearance" on:click|preventDefault={() => goto('/site_clearance')} class="menu-link">SITE
                CLEARANCE</a>
            <ul class={`dropdown ${group-hover-show}`}>
                <li>
                    <a href="/site_clearance#dangerous"
                       on:click|preventDefault={() => goto('/site_clearance#dangerous')} class="menu-link">Dangerous
                        Trees</a>
                </li>
                <li>
                    <a href="/site_clearance#line" on:click|preventDefault={() => goto('/site_clearance#line')}
                       class="menu-link">Line Clearance</a>
                </li>
            </ul>
        </li>
        <li>
            <a href="/contact" class="menu-link">CONTACT</a>
        </li>
    </ul>
</nav>

<style>
    /* Prevent default hover behavior on mobile */
    @media (hover: none) {
        .group:hover > .hidden {
            display: none; /* Disable hover on touch devices */
        }
    }
</style>

