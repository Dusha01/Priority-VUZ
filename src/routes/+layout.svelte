<script>
    import MainLayout from "$lib/layouts/MainLayout.svelte";
</script>

<div class="min-h-screen w-[100dvw] flex justify-center" id="main-layout">
    <MainLayout>
        <slot/>
    </MainLayout>
</div>