<script lang="ts">
    import { onMount } from 'svelte';
    
    let isVisible = false;
    let sectionRef: HTMLElement;
    
    const missionData = [
        {
            title: "Образование",
            description: "Формирование открытой образовательной экосистемы, направленной на гармоничное развитие конкурентоспособной личности обучающихся, владеющей передовыми мультидисциплинарными и кросс-отраслевыми технологиями, компетенциями цифровой экономики и межкультурного взаимодействия, способной генерировать новые знания, идеи и воплощать их в условиях быстроизменчивой внешней и внутренней среды.",
            color: 'blue'
        },
        {
            title: "Наука",
            description: "Лидерство в области научных исследований и разработок для транспорта за счёт создания коллективов учёных мирового уровня, работающих по приоритетным направлениям страны, позволяющих ответить на глобальные внешние и внутренние вызовы.",
            color: 'blue'
        },
        {
            title: "Третья миссия",
            description: "Драйвер развития Восточного экономического вектора экономики как центр компетенций по транспортным технологиям и логистическому взаимодействию.",
            color: 'blue'
        }
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

<section id="mission" class="py-12 md:py-24 bg-gray-50" bind:this={sectionRef}>
    <div class="container mx-auto px-4 sm:px-6 h-full">
        <div class="flex flex-col lg:flex-row gap-6 lg:gap-16 items-stretch h-full">
            <div class="hidden lg:flex lg:w-24 justify-center items-center">
                <h2 class="text-4xl font-bold writing-mode-vertical rotate-270 text-gray-800 tracking-wider whitespace-nowrap transition-all duration-1000 ease-[cubic-bezier(0.68,-0.55,0.27,1.55)]" 
                    class:opacity-0={!isVisible}
                    class:translate-x-[-20px]={!isVisible}
                    class:opacity-100={isVisible}
                    class:translate-x-0={isVisible}>
                    МИССИЯ
                </h2>
            </div>
            
            <div class="lg:hidden mb-6 text-center">
                <h2 class="text-3xl font-bold text-gray-800 tracking-wider transition-all duration-1000 ease-out"
                    class:opacity-0={!isVisible}
                    class:translate-y-[-20px]={!isVisible}
                    class:opacity-100={isVisible}
                    class:translate-y-0={isVisible}>
                    МИССИЯ
                </h2>
            </div>
            
            <div class="flex-1">
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4 sm:gap-6 md:gap-8">
                    {#each missionData as mission, i}
                        <div class="transition-all duration-1000 ease-out delay-{150 * (i + 1)}"
                            class:opacity-0={!isVisible}
                            class:translate-y-4={!isVisible}
                            class:opacity-100={isVisible}
                            class:translate-y-0={isVisible}>
                            <div class="bg-white p-4 sm:p-6 rounded-xl shadow-md sm:shadow-lg border-l-4 border-{mission.color}-500 hover:shadow-xl transition-shadow h-full flex flex-col">
                                <h3 class="text-xl sm:text-2xl font-bold mb-3 sm:mb-4 text-{mission.color}-600 uppercase tracking-wider text-center">
                                    {mission.title}
                                </h3>
                                <p class="text-base sm:text-lg text-gray-700 leading-relaxed text-center flex-grow">
                                    {mission.description}
                                </p>
                            </div>
                        </div>
                    {/each}
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

    @media (max-width: 640px) {
        .writing-mode-vertical {
            writing-mode: horizontal-tb;
            transform: none;
        }
    }
</style>