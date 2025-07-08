<script lang="ts">
    import { onMount } from 'svelte';
    
    let sticky = false;
    let menuHeight = 0;
    
    onMount(() => {
        const menu = document.querySelector('.menu_priority') as HTMLElement;
        if (menu) menuHeight = menu.offsetHeight;
        
        window.addEventListener('scroll', handleScroll);
        
        return () => {
            window.removeEventListener('scroll', handleScroll);
        };
    });
    
    function handleScroll() {
        const pageTop = document.querySelector('.page-top');
        if (!pageTop) return;
        
        const pageTopRect = pageTop.getBoundingClientRect();
        const pageTopBottom = pageTopRect.bottom + window.scrollY;
        
        sticky = window.scrollY > pageTopBottom - menuHeight;
    }
</script>

<nav class={`menu_priority w-full bg-white shadow-lg z-40 transition-all duration-300 ${sticky ? 'fixed top-0 left-0' : 'relative'}`}>
    <div class="container mx-auto">
        <div class="flex justify-center space-x-2 p-2 overflow-x-auto">
            <a href="#about" class="px-4 py-2 rounded-full hover:bg-gray-100 transition whitespace-nowrap">
                <span>О&nbsp;ПРОГРАММЕ</span>
            </a>
            <a href="#mission" class="px-4 py-2 rounded-full hover:bg-gray-100 transition whitespace-nowrap">
                <span>МИССИЯ</span>
            </a>
            <a href="#team" class="px-4 py-2 rounded-full hover:bg-gray-100 transition whitespace-nowrap">
                <span>КОМАНДА</span>
            </a>
            <a href="#project" class="px-4 py-2 rounded-full hover:bg-gray-100 transition whitespace-nowrap">
                <span>СТРАТЕГИЧЕСКИЙ ПРОЕКТ</span>
            </a>
            <a href="#page-bottom" class="px-4 py-2 rounded-full hover:bg-gray-100 transition whitespace-nowrap">
                <span>ПРОГРАММА РАЗВИТИЯ</span>
            </a>
            <a href="#reports" class="px-4 py-2 rounded-full hover:bg-gray-100 transition whitespace-nowrap">
                <span>ОТЧЁТЫ</span>
            </a>
        </div>
    </div>
</nav>

<style>
    .menu_priority {
        scrollbar-width: none; /* Firefox */
        -ms-overflow-style: none; /* IE 10+ */
    }
    .menu_priority::-webkit-scrollbar {
        display: none; /* Chrome/Safari/Webkit */
    }
</style>