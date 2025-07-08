<script lang="ts">
    import Header from '$lib/components/Header.svelte';
    import PageTop from '$lib/components/PageTop.svelte';
    import NavigationMenu from '$lib/components/NavigationMenu.svelte';
    import AboutSection from '$lib/components/AboutSection.svelte';
    import ScrollToTop from '$lib/components/ScrollToTop.svelte';
    import Mission from '$lib/components/Mission.svelte';
    import Team from '$lib/components/Team.svelte';
</script>

<Header />
<main>
    <PageTop />
    <NavigationMenu />
    <AboutSection />
    <Mission/>
    <Team/>
</main>
<ScrollToTop />

<style>
    main {
        padding-top: 76px;
    }
</style>