<script lang="ts">
    import { onMount } from 'svelte';

    import engineeringEconomicsLogo from '../assets/images/engineering.png';
    import targetLogo from '../assets/icons/target.png';
    import technoLogo from '../assets/icons/technologies.png';
    import resultsLogo from '../assets/icons/results.png';
    import indicatorsLogo from '../assets/icons/indicators.png';
    import partnersLogo from '../assets/icons/partners.png';
    import prioritetLogo from '../assets/logo/priority.png';
    import tabletLogo from '../assets/icons/tablet.png';
    
    import partner1 from '../assets/logo/1_1.jpg';
    import partner2 from '../assets/logo/1_1.jpg';
    import partner3 from '../assets/logo/1_2.png';
    import partner4 from '../assets/logo/1_3.png';
    import partner5 from '../assets/logo/1_4.png';
    import partner6 from '../assets/logo/1_5.jpg';
    import partner7 from '../assets/logo/1_6.png';
    import partner8 from '../assets/logo/1_8.png';
    import partner9 from '../assets/logo/1_9.png';
    import partner10 from '../assets/logo/1_10.png';
    import partner11 from '../assets/logo/1_10.png';
    import partner12 from '../assets/logo/1_10.png';

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
    class="project-engineering-economics py-12 bg-gray-50"
    bind:this={sectionRef}>

    <div class="container mx-auto px-4 flex">
        <div class="hidden lg:flex items-center justify-center w-24 min-h-[400px] mr-8 sticky top-[100px] transform -translate-y-0 self-start">
            <h2 class="text-4xl font-bold writing-mode-vertical lg:writing-mode-vertical rotate-270 text-gray-800 tracking-wider whitespace-nowrap transition-all duration-1000 ease-[cubic-bezier(0.68,-0.55,0.27,1.55)]"
                class:opacity-0={!isVisible}
                class:translate-x-[-20px]={!isVisible}
                class:opacity-100={isVisible}
                class:translate-x-0={isVisible}>
                Стратегический проект
            </h2>
        </div>
        
        <div class="flex-1">
            <div class="project-engineering-economics-top flex justify-between items-center mb-8 transition-all duration-700 ease-out"
                class:opacity-0={!isVisible}
                class:translate-y-10={!isVisible}
                class:opacity-100={isVisible}
                class:translate-y-0={isVisible}>
                <div class="flex items-center gap-4">
                    <img src={tabletLogo} alt="Инженерная экономика" class="h-10 w-auto">
                    <h4 class="text-4xl font-bold text-blue-600">#ИНЖЕНЕРНАЯ ЭКОНОМИКА</h4>
                </div>
                <div>
                    <img src={prioritetLogo} alt="Приоритет 2030" class="h-22 w-auto">
                </div>
            </div>

            <div class="project-engineering-economics-content grid md:grid-cols-3 gap-8 mb-8">
                <div class="project-engineering-economics-left md:col-span-1 transition-all duration-700 ease-out delay-100"
                    class:opacity-0={!isVisible}
                    class:translate-x-[-20px]={!isVisible}
                    class:opacity-100={isVisible}
                    class:translate-x-0={isVisible}>
                    <div class="relative mb-4">
                        <img src={engineeringEconomicsLogo} alt="Инженерная экономика" class="w-full rounded-lg shadow-md">
                        <span class="absolute bottom-4 right-4 bg-blue-600 text-white text-2xl font-bold rounded-full w-12 h-12 flex items-center justify-center">3</span>
                    </div>
                    <div class="space-y-4">
                        <p class="text-gray-700 font-bold text-lg">Проектное бюро</p>
                        <p class="text-gray-700">«Бизнес и предпринимательство»</p>
                    </div>
                </div>

                <div class="project-engineering-economics-main md:col-span-2 space-y-6">
                    <div class="grid md:grid-cols-2 gap-6">
                        <div class="bg-white p-6 rounded-xl shadow-md border-l-4 border-blue-500 transition-all duration-700 ease-out delay-200"
                            class:opacity-0={!isVisible}
                            class:translate-y-10={!isVisible}
                            class:opacity-100={isVisible}
                            class:translate-y-0={isVisible}>
                            <div class="flex items-start gap-4 mb-4">
                                <img src={targetLogo} alt="Цели" class="h-8 w-auto mt-1">
                                <h5 class="text-lg font-bold text-gray-800">ЦЕЛЬ:</h5>
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
                                    <img 
                                        src={partner} 
                                        alt={`Партнер ${i + 1}`} 
                                        class="w-full h-auto object-contain max-h-16 transition-all duration-300 hover:scale-105"
                                    >
                                {/each}
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