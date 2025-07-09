<script lang="ts">
    import Header from '$lib/components/Header.svelte';
    import PageTop from '$lib/components/PageTop.svelte';
    import NavigationMenu from '$lib/components/NavigationMenu.svelte';
    import AboutSection from '$lib/components/AboutSection.svelte';
    import ScrollToTop from '$lib/components/ScrollToTop.svelte';
    import Mission from '$lib/components/Mission.svelte';
    import Team from '$lib/components/Team.svelte';
    import StrategicProject from '$lib/components/StrategicProject.svelte';
</script>

<Header />
<main>
    <PageTop />
    <NavigationMenu />
    <AboutSection />
    <Mission/>
    <Team/>
    <StrategicProject/>
</main>
<ScrollToTop />