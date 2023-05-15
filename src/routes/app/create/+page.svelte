<script>
    import CatLoading from "$lib/assets/loading-cat.gif"
    import { currentUser, pb } from "$lib/pocketbase.js"
    import { onMount } from "svelte";

    let questions

    onMount(async () => {
        const questions = await pb.collection('questions').getFirstListItem('relation = $currentUser.id')
    })
    
</script>

<img src={CatLoading} alt="loading cat" />
