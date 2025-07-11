<script lang="ts">
    import '../app.css';
    import Header from '$lib/components/MainPage/Header.svelte';
    import Footer from '$lib/components/MainPage/Footer.svelte';
</script>

<div class="min-h-screen w-[100dvw] flex justify-center">
    <div class="w-full border border-gray-300">
        <Header/>
        <div>
            <slot/>
        </div>
        <Footer/>
    </div>
</div>