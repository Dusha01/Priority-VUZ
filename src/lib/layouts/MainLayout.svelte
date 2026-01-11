<script lang="ts">
    import '../../app.css';
    import Footer from '$lib/components/common/Footer.svelte';
    import Header from '$lib/components/common/Header.svelte';
    import ScrollToTop from '$lib/components/home/ui/ScrollToTop.svelte';
</script>

<div class="w-full border border-gray-300">
    <Header/>
    <div>
        <slot/>
    </div>
    <Footer/>

    <ScrollToTop/>
</div>