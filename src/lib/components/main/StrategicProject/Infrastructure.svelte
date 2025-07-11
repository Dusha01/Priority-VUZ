<script lang="ts">
    import { onMount } from 'svelte';

    import infrastructLogo from '../../../assets/images/infrastructure.png';
    import targetLogo from '../../../assets/icons/target.png';
    import technoLogo from '../../../assets/icons/technologies.png';
    import resultsLogo from '../../../assets/icons/results.png';
    import indicatorsLogo from '../../../assets/icons/indicators.png';
    import partnersLogo from '../../../assets/icons/partners.png';
    import prioritetLogo from '../../../assets/logo/priority.png';
    import tabletLogo from '../../../assets/icons/tablet.png';
    
    import lokoLogo from '../../../assets/logo/1_1.jpg';
    import rzdLogo from '../../../assets/logo/1_2.png';
    import poliTehLogo from '../../../assets/logo/1_3.png';
    import rusGidroLogo from '../../../assets/logo/1_4.png';
    import hzLogo1 from '../../../assets/logo/1_5.jpg';
    import setiLogo from '../../../assets/logo/1_6.png';
    import vnizhkLogo from '../../../assets/logo/1_8.png';
    import niasLogo from '../../../assets/logo/1_9.png';
    import hzLogo2 from '../../../assets/logo/1_10.png';

    type InfrastructItem = {
        id: string;
        text: string;
    }

    type ListItem = {
        text: string;
    }

    let isVisible = false;
    let sectionRef: HTMLElement;

    const infrastructItems: InfrastructItem[] = [
        {id: '2.1', text: 'Лаборатория управления надёжностью технических систем в условиях работы в Северной и Арктической зонах'},
        {id: '2.2', text: 'Лаборатория новых технологий и материалов для восстановления и создания объектов транспортной инфраструктуры и подвижного состава в экстремальных климатических условиях Арктики'},
        {id: '2.3', text: 'Цифровые электрические системы и инфраструктура'},
        {id: '2.4', text: 'Лаборатория геотехнического строительства на промерзающих многолетнемерзлых и оттаивающих грунтах в Дальневосточном федеральном округе и Арктике'}
    ];

    const goals: ListItem[] = [
        { text: 'оптимизация планово-предупредительной системы технического обслуживания и ремонта подвижного состава' }
    ];

    const technologies: ListItem[] = [
        { text: 'цифровые технологии управления надежностью и безопасностью' },
        { text: 'новые материалы и технологии восстановления и ремонта' },
        { text: 'цифровые электрические системы и инфраструктура' },
        { text: 'геотехнические решения для строительства в сложных климатических условиях' }
    ];

    const results: ListItem[] = [
        { text: '60+ публ./год – WoS, Scopus Q1, Q2' },
        { text: '100+ млн. руб/год – доход в бюджет' },
        { text: '6+ патентов на изобретение (способы и технологии)' },
        { text: '20+ аспирантов и докторантов' }
    ];

    const educationIndicators: ListItem[] = [
        { text: '5+ программы ВО' },
        { text: '1500+ студентов/год – контингент очнообучающихся' },
        { text: '8+ новых программ ДПО' },
        { text: '1000+ слушателей ДПО' }
    ];

    const partners = [
        lokoLogo, rzdLogo, poliTehLogo, rusGidroLogo,
        hzLogo1, setiLogo, vnizhkLogo, niasLogo,
        hzLogo2
    ];

    onMount(() => {
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

<section id="StrategicProject" class="py-8 sm:py-12 bg-gray-50" bind:this={sectionRef}>
    <div class="container mx-auto px-4 sm:px-6">
        <div class="lg:hidden mb-6 text-center transition-all duration-700 ease-out"
            class:opacity-0={!isVisible}
            class:translate-y-[-20px]={!isVisible}
            class:opacity-100={isVisible}
            class:translate-y-0={isVisible}>
            <h2 class="text-2xl sm:text-3xl font-bold text-gray-800">СТРАТЕГИЧЕСКИЙ ПРОЕКТ</h2>
        </div>
        
        <div class="flex flex-col lg:flex-row gap-6 lg:gap-8">
            <div class="hidden lg:flex items-center justify-center w-20 xl:w-24 min-h-[400px] sticky top-[100px] transform -translate-y-0 self-start">
                <h2 class="text-3xl xl:text-4xl font-bold writing-mode-vertical text-gray-800 tracking-wider whitespace-nowrap transition-all duration-1000 ease-[cubic-bezier(0.68,-0.55,0.27,1.55)]"
                    class:opacity-0={!isVisible}
                    class:translate-x-[-20px]={!isVisible}
                    class:opacity-100={isVisible}
                    class:translate-x-0={isVisible}>
                    СТРАТЕГИЧЕСКИЙ ПРОЕКТ
                </h2>
            </div>
            
            <div class="flex-1">
                <div class="flex flex-col sm:flex-row justify-between items-center gap-4 mb-6 sm:mb-8 transition-all duration-700 ease-out"
                    class:opacity-0={!isVisible}
                    class:translate-y-4={!isVisible}
                    class:opacity-100={isVisible}
                    class:translate-y-0={isVisible}>
                    <div class="flex items-center gap-3 sm:gap-4">
                        <img src={tabletLogo} alt="Инфраструктура" class="h-8 sm:h-10 w-auto" loading="lazy">
                        <h3 class="text-2xl sm:text-3xl xl:text-4xl font-bold text-blue-600">#ИНФРАСТРУКТУРА</h3>
                    </div>
                    <img src={prioritetLogo} alt="Приоритет 2030" class="h-16 sm:h-20 w-auto" loading="lazy">
                </div>
                
                <div class="grid md:grid-cols-3 gap-4 sm:gap-6 mb-6 sm:mb-8">
                    <div class="md:col-span-1 transition-all duration-700 ease-out delay-100"
                        class:opacity-0={!isVisible}
                        class:translate-x-[-10px]={!isVisible}
                        class:opacity-100={isVisible}
                        class:translate-x-0={isVisible}>
                        <div class="relative mb-3 sm:mb-4">
                            <img src={infrastructLogo} alt="Инфраструктура" class="w-full rounded-lg shadow-md" loading="lazy">
                            <span class="absolute bottom-3 right-3 bg-blue-600 text-white text-xl sm:text-2xl font-bold rounded-full w-10 h-10 sm:w-12 sm:h-12 flex items-center justify-center">2</span>
                        </div>
                        <div class="space-y-2 sm:space-y-3">
                            {#each infrastructItems as item}
                                <p class="text-sm sm:text-base text-gray-700 leading-snug sm:leading-relaxed">
                                    <span class="font-bold">{item.id}</span> {item.text}
                                </p>
                            {/each}
                        </div>
                    </div>
                    
                    <div class="md:col-span-2 space-y-4 sm:space-y-6">
                        <div class="grid sm:grid-cols-2 gap-4 sm:gap-6">
                            <div class="bg-white p-4 sm:p-6 rounded-lg sm:rounded-xl shadow-sm sm:shadow-md border-l-4 border-blue-500 transition-all duration-700 ease-out delay-200"
                                class:opacity-0={!isVisible}
                                class:translate-y-4={!isVisible}
                                class:opacity-100={isVisible}
                                class:translate-y-0={isVisible}>
                                <div class="flex items-start gap-3 sm:gap-4 mb-3 sm:mb-4">
                                    <img src={targetLogo} alt="Цели" class="h-6 sm:h-8 w-auto mt-1" loading="lazy">
                                    <h4 class="text-base sm:text-lg font-bold text-gray-800">ЦЕЛИ:</h4>
                                </div>
                                <div class="space-y-2 sm:space-y-3">
                                    {#each goals as goal}
                                        <div class="flex items-start gap-2">
                                            <span class="text-blue-500 font-bold mt-1">—</span>
                                            <span class="text-sm sm:text-base text-gray-700">{goal.text}</span>
                                        </div>
                                    {/each}
                                </div>
                            </div>
                            
                            <div class="bg-white p-4 sm:p-6 rounded-lg sm:rounded-xl shadow-sm sm:shadow-md border-l-4 border-blue-500 transition-all duration-700 ease-out delay-300"
                                class:opacity-0={!isVisible}
                                class:translate-y-4={!isVisible}
                                class:opacity-100={isVisible}
                                class:translate-y-0={isVisible}>
                                <div class="flex items-start gap-3 sm:gap-4 mb-3 sm:mb-4">
                                    <img src={technoLogo} alt="Технологии" class="h-6 sm:h-8 w-auto mt-1" loading="lazy">
                                    <h4 class="text-base sm:text-lg font-bold text-gray-800">ТЕХНОЛОГИИ:</h4>
                                </div>
                                <div class="space-y-2 sm:space-y-3">
                                    {#each technologies as tech}
                                        <div class="flex items-start gap-2">
                                            <span class="text-blue-500 font-bold mt-1">—</span>
                                            <span class="text-sm sm:text-base text-gray-700">{tech.text}</span>
                                        </div>
                                    {/each}
                                </div>
                            </div>
                        </div>
                        
                        <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-4 sm:gap-6">
                            <div class="bg-white p-4 sm:p-6 rounded-lg sm:rounded-xl shadow-sm sm:shadow-md border-l-4 border-blue-500 transition-all duration-700 ease-out delay-400"
                                class:opacity-0={!isVisible}
                                class:translate-y-4={!isVisible}
                                class:opacity-100={isVisible}
                                class:translate-y-0={isVisible}>
                                <div class="flex items-start gap-3 sm:gap-4 mb-3 sm:mb-4">
                                    <img src={resultsLogo} alt="Результаты" class="h-6 sm:h-8 w-auto mt-1" loading="lazy">
                                    <h4 class="text-base sm:text-lg font-bold text-gray-800">РЕЗУЛЬТАТЫ ИССЛЕДОВАНИЙ К 2030 ГОДУ:</h4>
                                </div>
                                <div class="space-y-2 sm:space-y-3">
                                    {#each results as result}
                                        <div class="flex items-start gap-2">
                                            <span class="text-blue-500 font-bold mt-1">—</span>
                                            <span class="text-sm sm:text-base text-gray-700">{result.text}</span>
                                        </div>
                                    {/each}
                                </div>
                            </div>
                            
                            <div class="bg-white p-4 sm:p-6 rounded-lg sm:rounded-xl shadow-sm sm:shadow-md border-l-4 border-blue-500 transition-all duration-700 ease-out delay-500"
                                class:opacity-0={!isVisible}
                                class:translate-y-4={!isVisible}
                                class:opacity-100={isVisible}
                                class:translate-y-0={isVisible}>
                                <div class="flex items-start gap-3 sm:gap-4 mb-3 sm:mb-4">
                                    <img src={indicatorsLogo} alt="Показатели" class="h-6 sm:h-8 w-auto mt-1" loading="lazy">
                                    <h4 class="text-base sm:text-lg font-bold text-gray-800">ПОКАЗАТЕЛИ ОБРАЗОВАНИЯ К 2030 ГОДУ:</h4>
                                </div>
                                <div class="space-y-2 sm:space-y-3">
                                    {#each educationIndicators as indicator}
                                        <div class="flex items-start gap-2">
                                            <span class="text-blue-500 font-bold mt-1">—</span>
                                            <span class="text-sm sm:text-base text-gray-700">{indicator.text}</span>
                                        </div>
                                    {/each}
                                </div>
                            </div>
                            
                            <div class="bg-white p-4 sm:p-6 rounded-lg sm:rounded-xl shadow-sm sm:shadow-md border-l-4 border-blue-500 transition-all duration-700 ease-out delay-600"
                                class:opacity-0={!isVisible}
                                class:translate-y-4={!isVisible}
                                class:opacity-100={isVisible}
                                class:translate-y-0={isVisible}>
                                <div class="flex items-center gap-3 sm:gap-4 mb-3 sm:mb-4">
                                    <img src={partnersLogo} alt="Партнеры" class="h-6 sm:h-8 w-auto" loading="lazy">
                                    <h4 class="text-base sm:text-lg font-bold text-gray-800">ПАРТНЁРЫ:</h4>
                                </div>
                                <div class="grid grid-cols-2 xs:grid-cols-3 sm:grid-cols-2 lg:grid-cols-3 gap-3 sm:gap-4">
                                    {#each partners as partner, i}
                                        <img src={partner} alt={`Партнер ${i + 1}`} 
                                             class="w-full h-auto object-contain max-h-12 sm:max-h-16 transition-all duration-300 hover:scale-105" 
                                             loading="lazy">
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
    
    @media (max-width: 1024px) {
        .writing-mode-vertical {
            writing-mode: horizontal-tb;
            transform: none;
        }
    }
</style>