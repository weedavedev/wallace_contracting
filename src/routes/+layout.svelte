<script>
    import '../styles/global.css';
    import {onMount} from 'svelte';
    import Navbar from '../lib/NavBar.svelte';
    import Footer from '../lib/Footer.svelte';

    let isLargeScreen = false;
    const checkScreenSize = () => {
        isLargeScreen = window.innerWidth >= 768;
    };

    onMount(() => {
        checkScreenSize(); // Initial check
        window.addEventListener('resize', checkScreenSize);

        return () => {
            window.removeEventListener('resize', checkScreenSize);
        };
    });

</script>

<style>

</style>

<head>
<!--    <title>{metadata.title}</title>-->
    <title>Wallace Contracting</title>
<!--    <meta name="description" content={metadata.description}>-->
</head>
<div class="main">
    <Navbar/>

    <div class="current_page_content">
        <slot/>
    </div>

    <Footer/>
</div>