<script lang="ts">
    import { onMount } from 'svelte';
    
    let visible = false;
    const scrollThreshold = 300; 
    
    onMount(() => {
        window.addEventListener('scroll', handleScroll);
        return () => window.removeEventListener('scroll', handleScroll);
    });
    
    function handleScroll() {
        visible = window.scrollY > scrollThreshold;
    }
    
    function scrollToTop() {
        window.scrollTo({
            top: 0,
            behavior: 'smooth'
        });
    }
</script>

<button
    class={`fixed bottom-8 cursor-pointer right-8 z-50 bg-red-600 text-white p-3 rounded-full shadow-lg transition-all duration-300 ${visible ? 'opacity-100 hover:bg-red-700 hover:scale-110' : 'opacity-0 pointer-events-none'}`}    on:click={scrollToTop}
    aria-label="Вернуться наверх">
    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 10l7-7m0 0l7 7m-7-7v18" />
    </svg>
</button>