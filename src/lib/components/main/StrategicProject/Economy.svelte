<script lang="ts">
    import { onMount } from 'svelte';

    import engineeringEconomicsLogo from '../../../assets/images/engineering.png';
    import targetLogo from '../../../assets/icons/target.png';
    import technoLogo from '../../../assets/icons/technologies.png';
    import resultsLogo from '../../../assets/icons/results.png';
    import indicatorsLogo from '../../../assets/icons/indicators.png';
    import partnersLogo from '../../../assets/icons/partners.png';
    import prioritetLogo from '../../../assets/logo/priority.png';
    import tabletLogo from '../../../assets/icons/tablet.png';
    
    import partner1 from '../../../assets/logo/1_1.jpg';
    import partner2 from '../../../assets/logo/1_1.jpg';
    import partner3 from '../../../assets/logo/1_2.png';
    import partner4 from '../../../assets/logo/1_3.png';
    import partner5 from '../../../assets/logo/1_4.png';
    import partner6 from '../../../assets/logo/1_5.jpg';
    import partner7 from '../../../assets/logo/1_6.png';
    import partner8 from '../../../assets/logo/1_8.png';
    import partner9 from '../../../assets/logo/1_9.png';
    import partner10 from '../../../assets/logo/1_10.png';
    import partner11 from '../../../assets/logo/1_10.png';
    import partner12 from '../../../assets/logo/1_10.png';

    type ListItem = {
        text: string;
    };

    let isVisible = false;
    let sectionRef: HTMLElement;
    let isMobile = false;

    const goals: ListItem[] = [
        { text: 'Дополнение технической экспертизы исследований в сфере развития транспортной и электроэнергетической инфраструктуры ДФО и Арктики, финансово-экономическим обоснованием инженерной идеи и развития творческой платформы высшего учебного заведения' }
    ];

    const technologies: ListItem[] = [
        { text: 'разработка экономических моделей инженерных и научно-технических решений' }
    ];

    const results: ListItem[] = [
        { text: '25+ публ./год – WoS, Scopus Q1, Q2' },
        { text: '30+ млн. руб/год – НИОКР' },
        { text: '3+ патентов на изобретение (способы и технологии)' },
        { text: '15+ аспирантов и докторантов' }
    ];

    const educationIndicators: ListItem[] = [
        { text: '2+ программы ВО' },
        { text: '300+ студентов/год – контингент очнообучающихся' },
        { text: '3+ новых программ ДПО' },
        { text: '215+ слушателей ДПО' }
    ];

    const partners = [
        partner1, partner2, partner3, partner4,
        partner5, partner6, partner7, partner8,
        partner9, partner10, partner11, partner12
    ];

    onMount(() => {
        isMobile = window.innerWidth <= 1024;
        
        const observer = new IntersectionObserver(
            (entries) => {
                entries.forEach((entry) => {
                    isVisible = entry.isIntersecting;
                });
            },
            { threshold: 0.1 }
        );

        if (sectionRef) {
            observer.observe(sectionRef);
        }
        
        return () => {
            if (sectionRef) {
                observer.unobserve(sectionRef);
            }
        };
    });
</script>

<section id="StrategicProject" class="py-6 sm:py-8 bg-gray-50" bind:this={sectionRef}>
    <div class="container mx-auto px-4 sm:px-6">
        <div class="hidden lg:flex xl:hidden items-center justify-center mb-6 transition-all duration-700 ease-out"
            class:opacity-0={!isVisible}
            class:translate-y-[-20px]={!isVisible}
            class:opacity-100={isVisible}
            class:translate-y-0={isVisible}>
            <h2 class="text-2xl sm:text-3xl font-bold text-gray-800">СТРАТЕГИЧЕСКИЙ ПРОЕКТ</h2>
        </div>
        
        <div class="lg:hidden mb-4 text-center transition-all duration-700 ease-out"
            class:opacity-0={!isVisible}
            class:translate-y-[-20px]={!isVisible}
            class:opacity-100={isVisible}
            class:translate-y-0={isVisible}>
            <h2 class="text-2xl font-bold text-gray-800">СТРАТЕГИЧЕСКИЙ ПРОЕКТ</h2>
        </div>
        
        <div class="flex flex-col lg:flex-row gap-4 lg:gap-6">
            <div class="hidden xl:flex items-center justify-center w-20 xl:w-24 min-h-[400px] sticky top-[100px] transform -translate-y-0 self-start">
                <h2 class="text-3xl xl:text-4xl font-bold writing-mode-vertical text-gray-800 tracking-wider whitespace-nowrap transition-all duration-1000 ease-[cubic-bezier(0.68,-0.55,0.27,1.55)]"
                    class:opacity-0={!isVisible}
                    class:translate-x-[-20px]={!isVisible}
                    class:opacity-100={isVisible}
                    class:translate-x-0={isVisible}>
                    СТРАТЕГИЧЕСКИЙ ПРОЕКТ
                </h2>
            </div>
            
            <div class="flex-1">
                <div class="flex flex-col sm:flex-row justify-between items-center gap-3 mb-4 sm:mb-6 transition-all duration-700 ease-out"
                    class:opacity-0={!isVisible}
                    class:translate-y-4={!isVisible}
                    class:opacity-100={isVisible}
                    class:translate-y-0={isVisible}>
                    <div class="flex items-center gap-2 sm:gap-3">
                        <img src={tabletLogo} alt="Инженерная экономика" class="h-7 sm:h-8 w-auto" loading="lazy" sizes="(max-width: 1024px) 28px, 32px">
                        <h3 class="text-xl sm:text-2xl lg:text-3xl font-bold text-blue-600">#ИНЖЕНЕРНАЯ ЭКОНОМИКА</h3>
                    </div>
                    <img src={prioritetLogo} alt="Приоритет 2030" class="h-14 sm:h-16 w-auto" loading="lazy" sizes="(max-width: 1024px) 56px, 64px">
                </div>
                
                <div class="grid md:grid-cols-3 gap-3 sm:gap-4 mb-4 sm:mb-6">
                    <div class="md:col-span-1 lg:col-span-1 transition-all duration-700 ease-out" class:delay-100={!isMobile}>
                        <div class="relative mb-2 sm:mb-3">
                            <img src={engineeringEconomicsLogo} alt="Инженерная экономика" class="w-full rounded-lg shadow-md" loading="lazy">
                            <span class="absolute bottom-2 right-2 bg-blue-600 text-white text-lg sm:text-xl font-bold rounded-full w-8 h-8 sm:w-10 sm:h-10 flex items-center justify-center">3</span>
                        </div>
                        <div class="space-y-1 sm:space-y-2">
                            <p class="text-xs sm:text-sm lg:text-base font-bold text-gray-700">Проектное бюро</p>
                            <p class="text-xs sm:text-sm lg:text-base text-gray-700">«Бизнес и предпринимательство»</p>
                        </div>
                    </div>
                    
                    <div class="md:col-span-2 lg:col-span-2 space-y-3 sm:space-y-4">
                        <div class="grid sm:grid-cols-2 gap-3 sm:gap-4">
                            <div class="bg-white p-3 sm:p-4 rounded-lg shadow-sm border-l-4 border-blue-500 transition-all duration-700 ease-out" class:delay-200={!isMobile}>
                                <div class="flex items-start gap-2 sm:gap-3 mb-2 sm:mb-3">
                                    <img src={targetLogo} alt="Цели" class="h-5 sm:h-6 w-auto mt-1" loading="lazy" sizes="(max-width: 1024px) 20px, 24px">
                                    <h4 class="text-sm sm:text-base font-bold text-gray-800">ЦЕЛЬ:</h4>
                                </div>
                                <div class="space-y-1 sm:space-y-2">
                                    {#each goals as goal}
                                        <div class="flex items-start gap-1">
                                            <span class="text-blue-500 font-bold mt-0.5">—</span>
                                            <span class="text-xs sm:text-sm text-gray-700">{goal.text}</span>
                                        </div>
                                    {/each}
                                </div>
                            </div>
                            
                            <div class="bg-white p-3 sm:p-4 rounded-lg shadow-sm border-l-4 border-blue-500 transition-all duration-700 ease-out" class:delay-300={!isMobile}>
                                <div class="flex items-start gap-2 sm:gap-3 mb-2 sm:mb-3">
                                    <img src={technoLogo} alt="Технологии" class="h-5 sm:h-6 w-auto mt-1" loading="lazy" sizes="(max-width: 1024px) 20px, 24px">
                                    <h4 class="text-sm sm:text-base font-bold text-gray-800">ТЕХНОЛОГИИ:</h4>
                                </div>
                                <div class="space-y-1 sm:space-y-2">
                                    {#each technologies as tech}
                                        <div class="flex items-start gap-1">
                                            <span class="text-blue-500 font-bold mt-0.5">—</span>
                                            <span class="text-xs sm:text-sm text-gray-700">{tech.text}</span>
                                        </div>
                                    {/each}
                                </div>
                            </div>
                        </div>
                        
                        <div class="grid sm:grid-cols-2 lg:grid-cols-2 xl:grid-cols-3 gap-3 sm:gap-4">
                            <div class="bg-white p-3 sm:p-4 rounded-lg shadow-sm border-l-4 border-blue-500 transition-all duration-700 ease-out" class:delay-400={!isMobile}>
                                <div class="flex items-start gap-2 sm:gap-3 mb-2 sm:mb-3">
                                    <img src={resultsLogo} alt="Результаты" class="h-5 sm:h-6 w-auto mt-1" loading="lazy" sizes="(max-width: 1024px) 20px, 24px">
                                    <h4 class="text-sm sm:text-base font-bold text-gray-800">РЕЗУЛЬТАТЫ К 2030:</h4>
                                </div>
                                <div class="space-y-1 sm:space-y-2">
                                    {#each results as result}
                                        <div class="flex items-start gap-1">
                                            <span class="text-blue-500 font-bold mt-0.5">—</span>
                                            <span class="text-xs sm:text-sm text-gray-700">{result.text}</span>
                                        </div>
                                    {/each}
                                </div>
                            </div>
                            
                            <div class="bg-white p-3 sm:p-4 rounded-lg shadow-sm border-l-4 border-blue-500 transition-all duration-700 ease-out" class:delay-500={!isMobile}>
                                <div class="flex items-start gap-2 sm:gap-3 mb-2 sm:mb-3">
                                    <img src={indicatorsLogo} alt="Показатели" class="h-5 sm:h-6 w-auto mt-1" loading="lazy" sizes="(max-width: 1024px) 20px, 24px">
                                    <h4 class="text-sm sm:text-base font-bold text-gray-800">ПОКАЗАТЕЛИ ОБРАЗОВАНИЯ:</h4>
                                </div>
                                <div class="space-y-1 sm:space-y-2">
                                    {#each educationIndicators as indicator}
                                        <div class="flex items-start gap-1">
                                            <span class="text-blue-500 font-bold mt-0.5">—</span>
                                            <span class="text-xs sm:text-sm text-gray-700">{indicator.text}</span>
                                        </div>
                                    {/each}
                                </div>
                            </div>
                            
                            <div class="bg-white p-3 sm:p-4 rounded-lg shadow-sm border-l-4 border-blue-500 transition-all duration-700 ease-out" class:delay-600={!isMobile}>
                                <div class="flex items-center gap-2 sm:gap-3 mb-2 sm:mb-3">
                                    <img src={partnersLogo} alt="Партнеры" class="h-5 sm:h-6 w-auto" loading="lazy" sizes="(max-width: 1024px) 20px, 24px">
                                    <h4 class="text-sm sm:text-base font-bold text-gray-800">ПАРТНЁРЫ:</h4>
                                </div>
                                <div class="grid grid-cols-2 xs:grid-cols-3 sm:grid-cols-3 lg:grid-cols-4 xl:grid-cols-3 gap-2 sm:gap-3">
                                    {#each partners as partner, i}
                                        <div class="flex items-center justify-center p-1">
                                            <img src={partner} alt={`Партнер ${i + 1}`} 
                                                 class="w-full h-auto max-h-10 sm:max-h-12 object-contain transition-all duration-300 hover:scale-105" 
                                                 loading="lazy">
                                        </div>
                                    {/each}
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>

<style>
    [class*="transition-all"] {
        transition-property: all;
        will-change: transform, opacity;
    }
    
    .writing-mode-vertical {
        writing-mode: vertical-rl;
        transform: rotate(180deg);
    }
    
    @media (max-width: 1280px) {
        .writing-mode-vertical {
            writing-mode: horizontal-tb;
            transform: none;
        }
    }
</style>