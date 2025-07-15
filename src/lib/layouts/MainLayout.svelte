<script lang="ts">
    import '../../app.css';
    import Footer from '$lib/components/common/Footer.svelte';
    import Header from '$lib/components/common/Header.svelte';
</script>

<div class="w-full border border-gray-300">
    <Header/>
    <div>
        <slot/>
    </div>
    <Footer/>
</div>