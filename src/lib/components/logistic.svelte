<script lang="ts">
    import { onMount } from 'svelte';
    
    import logisticLogo from '../assets/images/logistics.png';
    import targetLogo from '../assets/icons/target.png';
    import technoLogo from '../assets/icons/technologies.png';
    import resultsLogo from '../assets/icons/results.png';
    import indicatorsLogo from '../assets/icons/indicators.png';
    import partnersLogo from '../assets/icons/partners.png';
    import prioritetLogo from '../assets/logo/priority.png';
    import tabletLogo from '../assets/icons/tablet.png'
    
    import transLogo from '../assets/logo/1.png';
    import rzdLogo from '../assets/logo/2.jpg';
    import hzLogo from '../assets/logo/3.jpg';
    import fescoLogo from '../assets/logo/4.jpg';
    import hz_Logo from '../assets/logo/5.png';
    import planLogo from '../assets/logo/6.png';
    import otlkLogo from '../assets/logo/7.png';
    import HzLogo from '../assets/logo/8.png';
    import mtzLogo from '../assets/logo/9.jpg';
    import hzLogo_ from '../assets/logo/10.jpg';

    type LogisticsItem = {
        id: string;
        text: string;
    };

    type ListItem = {
        text: string;
    };

    let isVisible = false;
    let sectionRef: HTMLElement;

    const logisticsItems: LogisticsItem[] = [
        { id: '1.1', text: 'Исследовательская лаборатория по транспортным технологиям и логистическому взаимодействию' },
        { id: '1.2', text: 'Лаборатория маркетинговых исследований транспортного комплекса Дальневосточного региона' },
        { id: '1.3', text: 'IT-лаборатория аналитики и прогнозирования транспортных процессов и логистики' },
        { id: '1.4', text: 'Лаборатория интеллектуальных тормозных систем для вождения тяжеловесных поездов в условиях БАМа и субарктической зоны' }
    ];

    const goals: ListItem[] = [
        { text: 'создание модели прогнозирования освоения грузопотоков на Восточном полигоне России и её трансфер через инновации и кадровое сопровождение в реальный сектор экономики' },
        { text: 'совершенствование технологий повышения пропускной и провозной способности Байкало-Амурской магистрали и субарктической зоны' }
    ];

    const technologies: ListItem[] = [
        { text: 'нейросетевые и вероятностно-статистические технологии управления логистикой' },
        { text: 'новые расчетные модели грузопотоков' },
        { text: 'линейка приборной и конструкторской базы тормозного оборудования для тяжеловесных поездов' }
    ];

    const results: ListItem[] = [
        { text: '70+ публ./год – WoS, Scopus Q1, Q2' },
        { text: '130+ млн. руб/год – доход в бюджет' },
        { text: '5+ патентов на изобретение (способы и технологии)' },
        { text: '25+ аспирантов и докторантов' }
    ];

    const educationIndicators: ListItem[] = [
        { text: '4+ программы ВО' },
        { text: '1600+ студентов/год – контингент очнообучающихся' },
        { text: '7+ новых программ ДПО' },
        { text: '1200+ слушателей ДПО' }
    ];

    const partners = [
        transLogo, rzdLogo, hzLogo, fescoLogo, 
        hz_Logo, planLogo, otlkLogo, HzLogo, 
        mtzLogo, hzLogo_
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

<section 
    id="StrategicProject" 
    class="project-logistics py-12 bg-gray-50"
    bind:this={sectionRef}>

    <div class="container mx-auto px-4 flex">
        <div class="hidden lg:flex items-center justify-center w-24 min-h-[400px] mr-8 sticky top-1/2 transform -translate-y-1/2 self-start">
            <h2 class="text-4xl font-bold writing-mode-vertical lg:writing-mode-vertical rotate-270 text-gray-800 tracking-wider whitespace-nowrap transition-all duration-1000 ease-[cubic-bezier(0.68,-0.55,0.27,1.55)]"                class:opacity-0={!isVisible}
                class:translate-x-[-20px]={!isVisible}
                class:opacity-100={isVisible}
                class:translate-x-0={isVisible}>
                Стратегический проект
            </h2>
        </div>
        
        <div class="flex-1">
            <div class="project-logistics-top flex justify-between items-center mb-8 transition-all duration-700 ease-out"
                class:opacity-0={!isVisible}
                class:translate-y-10={!isVisible}
                class:opacity-100={isVisible}
                class:translate-y-0={isVisible}>
                <div class="flex items-center gap-4">
                    <img src={tabletLogo} alt="Логистика" class="h-10 w-auto">
                    <h4 class="text-4xl font-bold text-blue-600">#ЛОГИСТИКА</h4>
                </div>
                <div>
                    <img src={prioritetLogo} alt="Приоритет 2030" class="h-22 w-auto">
                </div>
            </div>
        
        <div class="project-logistics-content grid md:grid-cols-3 gap-8 mb-8">
            <div class="project-logistics-left md:col-span-1 transition-all duration-700 ease-out delay-100"
                class:opacity-0={!isVisible}
                class:translate-x-[-20px]={!isVisible}
                class:opacity-100={isVisible}
                class:translate-x-0={isVisible}>
                <div class="relative mb-4">
                    <img src={logisticLogo} alt="Логистика" class="w-full rounded-lg shadow-md">
                    <span class="absolute bottom-4 right-4 bg-blue-600 text-white text-2xl font-bold rounded-full w-12 h-12 flex items-center justify-center">1</span>
                </div>
                <div class="space-y-4">
                    {#each logisticsItems as item}
                        <p class="text-gray-700">
                            <span class="font-bold">{item.id}</span> {item.text}
                        </p>
                    {/each}
                </div>
            </div>

            <div class="project-logistics-main md:col-span-2 space-y-6">
                <div class="grid md:grid-cols-2 gap-6">
                    <div class="bg-white p-6 rounded-xl shadow-md border-l-4 border-blue-500 transition-all duration-700 ease-out delay-200"
                        class:opacity-0={!isVisible}
                        class:translate-y-10={!isVisible}
                        class:opacity-100={isVisible}
                        class:translate-y-0={isVisible}>
                        <div class="flex items-start gap-4 mb-4">
                            <img src={targetLogo} alt="Цели" class="h-8 w-auto mt-1">
                            <h5 class="text-lg font-bold text-gray-800">ЦЕЛИ:</h5>
                        </div>
                        <div class="space-y-3">
                            {#each goals as goal}
                                <div class="flex items-start gap-2">
                                    <span class="text-blue-500 font-bold">—</span>
                                    <span class="text-gray-700">{goal.text}</span>
                                </div>
                            {/each}
                        </div>
                    </div>

                    <div class="bg-white p-6 rounded-xl shadow-md border-l-4 border-blue-500 transition-all duration-700 ease-out delay-300"
                        class:opacity-0={!isVisible}
                        class:translate-y-10={!isVisible}
                        class:opacity-100={isVisible}
                        class:translate-y-0={isVisible}>
                        <div class="flex items-start gap-4 mb-4">
                            <img src={technoLogo} alt="Технологии" class="h-8 w-auto mt-1">
                            <h5 class="text-lg font-bold text-gray-800">ТЕХНОЛОГИИ:</h5>
                        </div>
                        <div class="space-y-3">
                            {#each technologies as tech}
                                <div class="flex items-start gap-2">
                                    <span class="text-blue-500 font-bold">—</span>
                                    <span class="text-gray-700">{tech.text}</span>
                                </div>
                            {/each}
                        </div>
                    </div>
                </div>

                <div class="grid md:grid-cols-3 gap-6">
                    <div class="bg-white p-6 rounded-xl shadow-md border-l-4 border-blue-500 md:col-span-1 transition-all duration-700 ease-out delay-400"
                        class:opacity-0={!isVisible}
                        class:translate-y-10={!isVisible}
                        class:opacity-100={isVisible}
                        class:translate-y-0={isVisible}>
                        <div class="flex items-start gap-4 mb-4">
                            <img src={resultsLogo} alt="Результаты" class="h-8 w-auto mt-1">
                            <h5 class="text-lg font-bold text-gray-800">РЕЗУЛЬТАТЫ ИССЛЕДОВАНИЙ К 2030 ГОДУ:</h5>
                        </div>
                        <div class="space-y-3">
                            {#each results as result}
                                <div class="flex items-start gap-2">
                                    <span class="text-blue-500 font-bold">—</span>
                                    <span class="text-gray-700">{result.text}</span>
                                </div>
                            {/each}
                        </div>
                    </div>

                    <div class="bg-white p-6 rounded-xl shadow-md border-l-4 border-blue-500 md:col-span-1 transition-all duration-700 ease-out delay-500"
                        class:opacity-0={!isVisible}
                        class:translate-y-10={!isVisible}
                        class:opacity-100={isVisible}
                        class:translate-y-0={isVisible}>
                        <div class="flex items-start gap-4 mb-4">
                            <img src={indicatorsLogo} alt="Показатели" class="h-8 w-auto mt-1">
                            <h5 class="text-lg font-bold text-gray-800">ПОКАЗАТЕЛИ ОБРАЗОВАНИЯ К 2030 ГОДУ:</h5>
                        </div>
                        <div class="space-y-3">
                            {#each educationIndicators as indicator}
                                <div class="flex items-start gap-2">
                                    <span class="text-blue-500 font-bold">—</span>
                                    <span class="text-gray-700">{indicator.text}</span>
                                </div>
                            {/each}
                        </div>
                    </div>

                    <div class="bg-white p-6 rounded-xl shadow-md border-l-4 border-blue-500 md:col-span-1 transition-all duration-700 ease-out delay-600"
                        class:opacity-0={!isVisible}
                        class:translate-y-10={!isVisible}
                        class:opacity-100={isVisible}
                        class:translate-y-0={isVisible}>
                        <div class="flex items-center gap-4 mb-4">
                            <img src={partnersLogo} alt="Партнеры" class="h-8 w-auto">
                            <h5 class="text-lg font-bold text-gray-800">ПАРТНЁРЫ:</h5>
                        </div>
                        <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-2 lg:grid-cols-3 gap-4">
                            {#each partners as partner, i}
                                <img src={partner} alt={`Партнер ${i + 1}`} class="w-full h-auto object-contain max-h-16 transition-all duration-300 hover:scale-105">
                            {/each}
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
</style>