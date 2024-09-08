<!-- src/routes/Navbar.svelte -->
<script>
    import {base} from '$app/paths';
    import {afterUpdate} from "svelte";
    import {goto} from '$app/navigation';

    afterUpdate(() => {
        console.log("Base path is:", base);
    }); // For debugging
</script>
<img src="/media/navbar_image.png" alt="Wallace Contracting">
<nav class="bg-gray-800 p-4">
    <ul class="flex space-x-4">
        <li>
            <a href="/" on:click|preventDefault={() => goto('/')} class="text-white hover:bg-gray-700 px-3 py-2 rounded">HOME</a>
        </li>
        <li class="relative group">
            <a href="/fencing" on:click|preventDefault={() => goto('/fencing')} class="text-white hover:bg-gray-700 px-3 py-2 rounded">FENCING</a>
            <ul class="absolute left-0 hidden group-hover:block bg-gray-800 mt-1 rounded shadow-lg">
                <li>
                    <a href="/fencing/stock" on:click|preventDefault={() => goto('/fencing/#stock')} class="block text-white hover:bg-gray-700 px-4 py-2">STOCK FENCE</a>
                </li>
                <li>
                    <a href="/fencing/deer" on:click|preventDefault={() => goto('/fencing/#deer')} class="block text-white hover:bg-gray-700 px-4 py-2">DEER FENCE</a>
                </li>
            </ul>
        </li>
        <li class="relative group">
            <a href="/site_clearance" on:click|preventDefault={() => goto('/site_clearance')} class="text-white hover:bg-gray-700 px-3 py-2 rounded">SITE CLEARANCE</a>
            <ul class="absolute left-0  group-hover:block bg-gray-800 mt-1 rounded shadow-lg hidden">
                <li>
                    <a href="/site_clearance/dangerous" on:click|preventDefault={() => goto('/site_clearance/#dangerousTrees')} class="block text-white hover:bg-gray-700 px-4 py-2">DANGEROUS TREES</a>
                </li>
                <li>
                    <a href="/site_clearance/line" on:click|preventDefault={() => goto('/site_clearance/#LineClearance')} class="block text-white hover:bg-gray-700 px-4 py-2">LINE CLEARANCE</a>
                </li>
            </ul>
        </li>
        <li>
            <a href="/contact" on:click|preventDefault={() => goto('/contact')} class="text-white hover:bg-gray-700 px-3 py-2 rounded">CONTACT</a>
        </li>
    </ul>
</nav>

<style>
</style>