<script lang="ts">
    import { onMount } from 'svelte';

    let isVisible = false;
    let sectionRef: HTMLElement;

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
    
    const teamMembers = [
        {
            name: "Владимир Буровцев",
            title: "Ректор, руководитель программы развития",
            imageUrl: "/src/lib/assets/humans/Burovtsev.jpg",
        },
        {
            name: "Аркадий Едигарян",
            title: "Первый проректор",
            imageUrl: "/src/lib/assets/humans/Yedigaryan.jpg",
        },
        {
            name: "Артём Пляскин",
            title: "Проректор по учебной работе",
            imageUrl: "/src/lib/assets/humans/Plyaskin.jpg",
        },
        {
            name: "Иван Игнатенко",
            title: "Проректор по научной работе",
            imageUrl: "/src/lib/assets/humans/Ignatenko.jpg",
        },
        {
            name: "Алексей Кушнирук",
            title: "Руководитель проектного офиса",
            imageUrl: "/src/lib/assets/humans/Kushniruk.jpg",
        },
        {
            name: "Роман Король",
            title: "Руководитель направления стратегического проекта «Исследовательская лаборатория по транспортным технологиям и логистическому взаимодействию»",
            imageUrl: "/src/lib/assets/humans/Korol.jpg",
        },
        {
            name: "Елена Химич",
            title: "Руководитель направления стратегического проекта «Лаборатория маркетинговых исследований транспортного комплекса Дальневосточного региона»",
            imageUrl: "/src/lib/assets/humans/Himich.jpg",
        },
        {
            name: "Юлия Пономарчук",
            title: "Руководитель направления стратегического проекта «IT-лаборатория аналитики и прогнозирования транспортных процессов и логистики»",
            imageUrl: "/src/lib/assets/humans/Ponomarchuk.jpg",
        },
        {
            name: "Максим Кейно",
            title: "Руководитель направления стратегического проекта «Лаборатория интеллектуальных тормозных систем для вождения тяжеловесных поездов в условиях БАМа и субарктической зоны»",
            imageUrl: "/src/lib/assets/humans/Keyno.jpg",
        },
        {
            name: "Алексей Барчуков",
            title: "Руководитель направления стратегического проекта «Инженерная экономика»",
            imageUrl: "/src/lib/assets/humans/Barchukov.jpg",
        },
        {
            name: "Юрий Давыдов",
            title: "Руководитель направления стратегического проекта «Лаборатория управления надёжностью технических систем в условиях работы в Северной и Арктической зонах»",
            imageUrl: "/src/lib/assets/humans/Davyduv.jpg",
        },
        {
            name: "Александр Лукьянчук",
            title: "Руководитель направления стратегического проекта «Лаборатория новых технологий и материалов для восстановления и создания объектов транспортной инфраструктуры и подвижного состава»",
            imageUrl: "/src/lib/assets/humans/Lukyanchuk.jpg",
        },
        {
            name: "Евгений Трапкин",
            title: "Руководитель направления стратегического проекта «Цифровые электрические системы и инфраструктура»",
            imageUrl: "/src/lib/assets/humans/Tryapkin.jpg",
        },
        {
            name: "Сергей Кудрявцев",
            title: "Руководитель направления стратегического проекта «Лаборатория геотехнического строительства на промерзающих многолетнемерзлых и оттаивающих грунтах в ДФО и Арктике»",
            imageUrl: "/src/lib/assets/humans/kudryavcev.jpg",
        },
        {
            name: "Валентина Комарова",
            title: "Руководитель направления стратегического проекта «Университет кадровых трансформаций»",
            imageUrl: "/src/lib/assets/humans/Komarova.jpg",
        },
    ];
</script>

<section id="team" class="py-12 sm:py-16 md:py-20 lg:py-24 bg-gray-100" bind:this={sectionRef}>
    <div class="container mx-auto px-4 sm:px-6 h-full">
        <div class="flex flex-col lg:flex-row gap-6 sm:gap-8 lg:gap-12 xl:gap-16 items-stretch h-full">
            <div class="hidden lg:flex items-center justify-center w-24 min-h-[400px] mr-8 sticky top-[100px] transform -translate-y-0 self-start">
                <h2 class="text-4xl font-bold writing-mode-vertical lg:writing-mode-vertical rotate-270 text-gray-800 tracking-wider whitespace-nowrap transition-all duration-1000 ease-[cubic-bezier(0.68,-0.55,0.27,1.55)]"
                    class:opacity-0={!isVisible}
                    class:translate-x-[-20px]={!isVisible}
                    class:opacity-100={isVisible}
                    class:translate-x-0={isVisible}>
                    КОМАНДА
                </h2>
            </div>
            
            <div class="lg:hidden mb-4 text-center">
                <h2 class="text-3xl sm:text-4xl font-bold text-gray-800 tracking-wider">
                    КОМАНДА
                </h2>
            </div>

            <div class="flex-1 grid grid-cols-1 xs:grid-cols-2 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 xl:grid-cols-5 gap-4 sm:gap-5 md:gap-6">
                {#each teamMembers as member}
                    <div class="bg-white rounded-lg shadow-md overflow-hidden hover:shadow-lg transform hover:scale-[1.02] transition-all duration-200 flex flex-col">
                        <div class="flex justify-center pt-4 px-4">
                            <img 
                                src={member.imageUrl} 
                                alt={member.name} 
                                class="w-32 h-28 sm:w-36 sm:h-32 md:w-40 md:h-36 object-cover object-center rounded-lg" 
                            />
                        </div>
                        <div class="p-3 sm:p-4 flex-grow">
                            <h3 class="text-sm sm:text-base md:text-lg font-semibold text-gray-800 mb-1 sm:mb-2">{member.name}</h3>
                            <p class="text-xs sm:text-sm text-gray-600 leading-tight sm:leading-snug">{member.title}</p>
                        </div>
                    </div>
                {/each}
            </div>
        </div>
    </div>
</section>