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
    class="py-4 md:py-8 bg-gray-50"
    bind:this={sectionRef}>
    
    <div class="container mx-auto px-4">
        <div class="mb-4 md:mb-6 text-center transition-all duration-700 ease-out"
            class:opacity-0={!isVisible}
            class:translate-y-[-20px]={!isVisible}
            class:opacity-100={isVisible}
            class:translate-y-0={isVisible}>
            <h2 class="text-2xl md:text-3xl font-bold text-gray-800">СТРАТЕГИЧЕСКИЙ ПРОЕКТ</h2>
        </div>
        
        <div class="flex flex-col gap-4 md:gap-6">
            <div class="flex-1">
                <!-- Шапка проекта -->
                <div class="flex flex-col md:flex-row justify-between items-center gap-3 mb-4 md:mb-6 transition-all duration-700 ease-out"
                    class:opacity-0={!isVisible}
                    class:translate-y-4={!isVisible}
                    class:opacity-100={isVisible}
                    class:translate-y-0={isVisible}>
                    <div class="flex items-center gap-2 md:gap-3">
                        <img src={tabletLogo} alt="Инженерная экономика" class="h-8 md:h-10 w-auto" loading="lazy">
                        <h3 class="text-xl md:text-3xl font-bold text-blue-600">#ИНЖЕНЕРНАЯ ЭКОНОМИКА</h3>
                    </div>
                    <img src={prioritetLogo} alt="Приоритет 2030" class="h-16 md:h-20 w-auto mt-2 md:mt-0" loading="lazy">
                </div>
                
                <div class="grid grid-cols-1 md:grid-cols-3 gap-4 mb-6">
                    <div class="transition-all duration-700 ease-out delay-100"
                        class:opacity-0={!isVisible}
                        class:translate-x-[-10px]={!isVisible}
                        class:opacity-100={isVisible}
                        class:translate-x-0={isVisible}>
                        <div class="relative mb-3 md:mb-4">
                            <img src={engineeringEconomicsLogo} alt="Инженерная экономика" class="w-full rounded-lg shadow-md" loading="lazy">
                            <span class="absolute bottom-2 right-2 md:bottom-3 md:right-3 bg-blue-600 text-white text-xl md:text-2xl font-bold rounded-full w-10 h-10 md:w-12 md:h-12 flex items-center justify-center">3</span>
                        </div>
                        <div class="space-y-2 md:space-y-3">
                            <p class="text-base md:text-lg font-bold text-gray-700">Проектное бюро</p>
                            <p class="text-sm md:text-base text-gray-700">«Бизнес и предпринимательство»</p>
                        </div>
                    </div>
                    
                    <div class="col-span-1 md:col-span-2 space-y-3 md:space-y-4">
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-3 md:gap-4">
                            <div class="bg-white p-4 md:p-6 rounded-xl shadow-md border-l-4 border-blue-500 transition-all duration-700 ease-out delay-200"
                                class:opacity-0={!isVisible}
                                class:translate-y-4={!isVisible}
                                class:opacity-100={isVisible}
                                class:translate-y-0={isVisible}>
                                <div class="flex items-start gap-3 md:gap-4 mb-3 md:mb-4">
                                    <img src={targetLogo} alt="Цели" class="h-6 md:h-8 w-auto mt-1" loading="lazy">
                                    <h4 class="text-base md:text-lg font-bold text-gray-800">ЦЕЛЬ:</h4>
                                </div>
                                <div class="space-y-2 md:space-y-3">
                                    {#each goals as goal}
                                        <div class="flex items-start gap-2">
                                            <span class="text-blue-500 font-bold mt-1">—</span>
                                            <span class="text-sm md:text-base text-gray-700">{goal.text}</span>
                                        </div>
                                    {/each}
                                </div>
                            </div>
                            
                            <div class="bg-white p-4 md:p-6 rounded-xl shadow-md border-l-4 border-blue-500 transition-all duration-700 ease-out delay-300"
                                class:opacity-0={!isVisible}
                                class:translate-y-4={!isVisible}
                                class:opacity-100={isVisible}
                                class:translate-y-0={isVisible}>
                                <div class="flex items-start gap-3 md:gap-4 mb-3 md:mb-4">
                                    <img src={technoLogo} alt="Технологии" class="h-6 md:h-8 w-auto mt-1" loading="lazy">
                                    <h4 class="text-base md:text-lg font-bold text-gray-800">ТЕХНОЛОГИИ:</h4>
                                </div>
                                <div class="space-y-2 md:space-y-3">
                                    {#each technologies as tech}
                                        <div class="flex items-start gap-2">
                                            <span class="text-blue-500 font-bold mt-1">—</span>
                                            <span class="text-sm md:text-base text-gray-700">{tech.text}</span>
                                        </div>
                                    {/each}
                                </div>
                            </div>
                        </div>
                        
                        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-3 md:gap-4">
                            <div class="bg-white p-4 md:p-6 rounded-xl shadow-md border-l-4 border-blue-500 transition-all duration-700 ease-out delay-400"
                                class:opacity-0={!isVisible}
                                class:translate-y-4={!isVisible}
                                class:opacity-100={isVisible}
                                class:translate-y-0={isVisible}>
                                <div class="flex items-start gap-3 md:gap-4 mb-3 md:mb-4">
                                    <img src={resultsLogo} alt="Результаты" class="h-6 md:h-8 w-auto mt-1" loading="lazy">
                                    <h4 class="text-base md:text-lg font-bold text-gray-800">РЕЗУЛЬТАТЫ К 2030:</h4>
                                </div>
                                <div class="space-y-2 md:space-y-3">
                                    {#each results as result}
                                        <div class="flex items-start gap-2">
                                            <span class="text-blue-500 font-bold mt-1">—</span>
                                            <span class="text-sm md:text-base text-gray-700">{result.text}</span>
                                        </div>
                                    {/each}
                                </div>
                            </div>
                            
                            <div class="bg-white p-4 md:p-6 rounded-xl shadow-md border-l-4 border-blue-500 transition-all duration-700 ease-out delay-500"
                                class:opacity-0={!isVisible}
                                class:translate-y-4={!isVisible}
                                class:opacity-100={isVisible}
                                class:translate-y-0={isVisible}>
                                <div class="flex items-start gap-3 md:gap-4 mb-3 md:mb-4">
                                    <img src={indicatorsLogo} alt="Показатели" class="h-6 md:h-8 w-auto mt-1" loading="lazy">
                                    <h4 class="text-base md:text-lg font-bold text-gray-800">ПОКАЗАТЕЛИ ОБРАЗОВАНИЯ:</h4>
                                </div>
                                <div class="space-y-2 md:space-y-3">
                                    {#each educationIndicators as indicator}
                                        <div class="flex items-start gap-2">
                                            <span class="text-blue-500 font-bold mt-1">—</span>
                                            <span class="text-sm md:text-base text-gray-700">{indicator.text}</span>
                                        </div>
                                    {/each}
                                </div>
                            </div>
                            
                            <div class="bg-white p-4 md:p-6 rounded-xl shadow-md border-l-4 border-blue-500 sm:col-span-2 lg:col-span-1 transition-all duration-700 ease-out delay-600"
                                class:opacity-0={!isVisible}
                                class:translate-y-4={!isVisible}
                                class:opacity-100={isVisible}
                                class:translate-y-0={isVisible}>
                                <div class="flex items-center gap-3 md:gap-4 mb-3 md:mb-4">
                                    <img src={partnersLogo} alt="Партнеры" class="h-6 md:h-8 w-auto" loading="lazy">
                                    <h4 class="text-base md:text-lg font-bold text-gray-800">ПАРТНЁРЫ:</h4>
                                </div>
                                <div class="grid grid-cols-3 sm:grid-cols-4 lg:grid-cols-3 gap-3 md:gap-4">
                                    {#each partners as partner, i}
                                        <img src={partner} alt={`Партнер ${i + 1}`} 
                                             class="w-full h-auto max-h-12 md:max-h-16 object-contain transition-all duration-300 hover:scale-105" 
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
</style>