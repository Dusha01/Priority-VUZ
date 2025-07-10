<script lang="ts">
    import Header from '$lib/components/Header.svelte';
    import PageTop from '$lib/components/section_1.svelte';
    import NavigationMenu from '$lib/components/NavigationMenu.svelte';
    import AboutSection from '$lib/components/section_2.svelte';
    import ScrollToTop from '$lib/components/utils/ScrollToTop.svelte';
    import Mission from '$lib/components/section_3.svelte';
    import Team from '$lib/components/section_4.svelte';
    import Logistic from '$lib/components/section_5/logistic.svelte';
    import Infrastruct from '$lib/components/section_5/infrastruct.svelte';
    import Economy from '$lib/components/section_5/economy.svelte';
    import Growth from '$lib/components/section_6.svelte';
    import Footer from '$lib/components/Footer.svelte';

</script>


<Header />

<main>
    <PageTop />
    <NavigationMenu />
    <AboutSection />
    <Mission/>
    <Team/>
    <Logistic/>
    <Infrastruct/>
    <Economy/>
    <Growth/>
</main>

<Footer/>
<ScrollToTop />
