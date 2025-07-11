<script lang="ts">
    import '../app.css';
    import Header from '$lib/components/MainPage/Header.svelte';
    import Footer from '$lib/components/MainPage/Footer.svelte';
</script>

<div class="min-h-screen flex flex-col">
    <Header/>

    <main class="flex-grow">
        <slot/>
    </main>

    <Footer/>
</div>