<script lang="ts">
    import ArrowDown from './ui/ArrowDown.svelte';
    import sectionBg from '../../assets/bg/section_1_bg.jpg';
    import { onMount } from 'svelte';
    
    let sticky = false;
    
    onMount(() => {
        const handleScroll = () => {
            const pageTop = document.querySelector('.page-top') as HTMLElement; 
            if (!pageTop) return;
            
            const pageTopRect = pageTop.getBoundingClientRect();
            const pageTopBottom = pageTopRect.bottom + window.scrollY;
            const menuHeight = document.querySelector('.menu_priority')?.clientHeight || 0;
            
            sticky = window.scrollY > pageTopBottom - menuHeight;
        };
        
        window.addEventListener('scroll', handleScroll);
        handleScroll();
        
        return () => window.removeEventListener('scroll', handleScroll);
    });
</script>

<section 
    class="page-top min-h-screen flex flex-col justify-between pt-32 pb-16 px-4 relative"
    style="background: linear-gradient(rgba(255, 255, 255, 0.7), rgba(255, 255, 255, 0.7)), url('{sectionBg}'); background-size: cover; background-position: center;">
    <div class="page-top_main max-w-2xl text-left ml-4 md:ml-8 lg:ml-16 mt-16">
        <h1 class="text-4xl md:text-5xl font-bold mb-4 text-red-600">
            ПРОГРАММА РАЗВИТИЯ УНИВЕРСИТЕТА
        </h1>
        <p class="text-2xl md:text-3xl font-bold text-black">
            НА 2023–2030 ГОДЫ В РАМКАХ РЕАЛИЗАЦИИ ПРОГРАММЫ
            СТРАТЕГИЧЕСКОГО АКАДЕМИЧЕСКОГО ЛИДЕРСТВА «ПРИОРИТЕТ-2030»
        </p>
    </div>

    <div class="page-top_end max-w-2xl text-right self-end mr-4 md:mr-8 lg:mr-16 mb-16">
        <h2 class="text-3xl md:text-4xl font-bold text-blue-600 mb-4">
            СТРАТЕГИЧЕСКАЯ ЦЕЛЬ
        </h2>
        <p class="text-xl md:text-2xl font-bold text-black">
            ТРАНСФОРМАЦИЯ В УНИВЕРСИТЕТ СТРАТЕГИЧЕСКОГО АКАДЕМИЧЕСКОГО ЛИДЕРСТВА ДАЛЬНЕГО ВОСТОКА В ОБЛАСТИ ОБРАЗОВАНИЯ И НАУКИ
        </p>
    </div>

    <a href="#about" class="self-center mb-8">
        <ArrowDown />
    </a>
</section>

<style>
    .page-top {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
    }
    
    @media (max-width: 768px) {
        .page-top_main, .page-top_end {
            max-width: 100%;
            margin-left: 1rem;
            margin-right: 1rem;
        }
        
        .page-top_main h1 {
            font-size: 2rem;
        }
        
        .page-top_main p {
            font-size: 1.25rem;
        }
        
        .page-top_end h2 {
            font-size: 1.5rem;
        }
        
        .page-top_end p {
            font-size: 1rem;
        }
    }
</style>