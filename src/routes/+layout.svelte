<script>
    // import {mediaSource} from '$lib/constants';
    import '../styles/global.css';
    import {onMount} from 'svelte';

    // let backgroundImage = `${mediaSource}/lisa_background_cropped.jpg`;
    // let backgroundImageMobile = `${mediaSource}/lisa_background_mobile.jpg`;
    //console.log(backgroundImage)
    let isLargeScreen = false;


    // Function to check screen size
    const checkScreenSize = () => {
        isLargeScreen = window.innerWidth >= 768;
    };

    // Check on mount and add resize event listener
    onMount(() => {
        checkScreenSize(); // Initial check
        window.addEventListener('resize', checkScreenSize);

        return () => {
            window.removeEventListener('resize', checkScreenSize);
        };
    });
</script>

<style>
    /* Global styles or additional styling for the component can go here */
    .background_image {
        background-size: cover;
        background-position: center;
        height: 100vh; /* Full height */
        width: 100%; /* Full width */
    }

    .main {
        align-content: center;
        width: 95vw;
        height: 100vh;
    }

    .holding_page_content {
        display: flex; /* Use flexbox for layout */
        flex-wrap: wrap; /* Allow wrapping of columns if needed (responsive) */
        margin: 0;
        height: 100vh;
        width: 100%;
    }

</style>

<div class={`main background_image ${isLargeScreen ? 'bg-[url(/media/lisa_background_cropped.jpg)]' : 'bg-[url(/media/lisa_background_mobile.jpg)]'}`}>
    <!--    <Navbar/>   -->
    <div class="holding_page_content ">
        <slot/>
    </div>
    <!--    <Footer/>   -->
</div>