<script lang="ts">
    import '../../app.css';
    import Footer from '$lib/components/common/Footer.svelte';
</script>

<div class="w-full border border-gray-300">
    <div>
        <slot/>
    </div>
    <Footer/>
</div>