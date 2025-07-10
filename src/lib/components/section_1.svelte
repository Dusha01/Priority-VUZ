<script lang="ts">
    import ArrowDown from './utils/ArrowDown.svelte';
    import sectionBg from '$lib/assets/bg/section_1_bg.jpg';
    import { onMount } from 'svelte';
    
    let visible = false;
    let arrowVisible = false;
    let borderVisible = false;
    
    onMount(() => {
        const handleScroll = () => {
            const section = document.querySelector('.page-top');
            if (!section) return;
            
            const rect = section.getBoundingClientRect();
            const isInView = rect.top < window.innerHeight && rect.bottom >= 0;
            
            if (isInView) {
                visible = true;
                setTimeout(() => borderVisible = true, 1300);
                setTimeout(() => arrowVisible = true, 1500);
            } else {
                visible = false;
                borderVisible = false;
                arrowVisible = false;
            }
        };
        
        window.addEventListener('scroll', handleScroll);
        handleScroll(); 
        
        return () => window.removeEventListener('scroll', handleScroll);
    });
</script>

<section 
    class="page-top min-h-screen flex flex-col justify-between pt-32 pb-16 px-4 relative"
    style="background: linear-gradient(rgba(255, 255, 255, 0.7), rgba(255, 255, 255, 0.7)), url('{sectionBg}'); background-size: cover; background-position: center;"
>
    <div class="page-top_main max-w-2xl text-left ml-4 md:ml-8 lg:ml-16 mt-16 overflow-hidden">
        <h1 
            class="text-4xl md:text-5xl font-bold mb-4 text-red-600 transition-all duration-1000 ease-out {visible ? 'translate-x-0 opacity-100' : '-translate-x-full opacity-0'}"
        >
            ПРОГРАММА РАЗВИТИЯ УНИВЕРСИТЕТА
        </h1>
        <p 
            class="text-2xl md:text-3xl font-bold text-black transition-all duration-1000 ease-out delay-200 {visible ? 'translate-x-0 opacity-100' : '-translate-x-full opacity-0'}"
        >
            НА 2023–2030 ГОДЫ В РАМКАХ РЕАЛИЗАЦИИ ПРОГРАММЫ
            СТРАТЕГИЧЕСКОГО АКАДЕМИЧЕСКОГО ЛИДЕРСТВА «ПРИОРИТЕТ-2030»
        </p>
    </div>

    <div class="page-top_end max-w-2xl text-right self-end mr-4 md:mr-8 lg:mr-16 mb-16 overflow-hidden">
        <h2 
            class="text-3xl md:text-4xl font-bold text-blue-600 mb-4 transition-all duration-1000 ease-out delay-400 {visible ? 'translate-x-0 opacity-100' : 'translate-x-full opacity-0'}"
        >
            СТРАТЕГИЧЕСКАЯ ЦЕЛЬ
        </h2>
        <p 
            class="text-xl md:text-2xl font-bold text-black transition-all duration-1000 ease-out delay-600 {visible ? 'translate-x-0 opacity-100' : 'translate-x-full opacity-0'}"
        >
            ТРАНСФОРМАЦИЯ В УНИВЕРСИТЕТ СТРАТЕГИЧЕСКОГО АКАДЕМИЧЕСКОГО ЛИДЕРСТВА ДАЛЬНЕГО ВОСТОКА В ОБЛАСТИ ОБРАЗОВАНИЯ И НАУКИ
        </p>
    </div>

    <a 
        href="#about" 
        class="self-center mb-8 relative transition-all duration-500 {arrowVisible ? 'opacity-100' : 'opacity-0'}"
    >
        <div class="absolute inset-0 flex items-center justify-center">
            <div class="absolute border-2 border-transparent rounded-full transition-all duration-700 {borderVisible ? 'w-16 h-16 border-red-600' : 'w-8 h-8'}"></div>
            <div class="absolute border-2 border-transparent rounded-full transition-all duration-1000 delay-300 {borderVisible ? 'w-20 h-20 border-blue-600' : 'w-8 h-8'}"></div>
        </div>
        <ArrowDown />
    </a>
</section>

<style>
    .page-top {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
    }
    
    .page-top_main, .page-top_end {
        will-change: transform;
    }
    
    .page-top_main h1, .page-top_main p,
    .page-top_end h2, .page-top_end p {
        will-change: transform, opacity;
    }
    
    a[href="#about"] {
        will-change: opacity;
    }
</style>