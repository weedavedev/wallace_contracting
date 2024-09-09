<script>
    import {base} from '$app/paths';

    // Use the base path to reference images directly
    let localImages = [
        {src: `${base}/media/gallery/fencing/fencing_1.png`, alt: 'Image 1'},
        {src: `${base}/media/gallery/fencing/fencing_2.png`, alt: 'Image 2'},
        {src: `${base}/media/gallery/fencing/fencing_3.png`, alt: 'Image 3'},
        // Add additional images here
    ];

    function handleImageClick(index) {
        // Handle image click event
    }
</script>

<link rel="stylesheet" href="main.css">

<div class="gallery-container">
    {#each localImages as image, index}
        <img src={image.src} alt={image.alt} on:click={() => handleImageClick(index)}/>
    {/each}
</div>

<style>
    .gallery-container {
        @apply grid grid-cols-1 gap-4 md:grid-cols-2 xl:grid-cols-3;
    }


    .gallery-image img {
        @apply object-cover rounded-md;
    }
</style>