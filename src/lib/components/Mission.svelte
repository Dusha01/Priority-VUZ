<script>
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
</script>

<section id="mission" class="py-24 bg-gray-50">
    <div class="container mx-auto px-4 h-full">
        <div class="flex flex-col lg:flex-row gap-8 lg:gap-16 items-stretch h-full">
            <div class="lg:w-24 flex justify-center items-center">
                <h2 class="text-4xl font-bold writing-mode-vertical lg:writing-mode-vertical rotate-270 text-gray-800 tracking-wider whitespace-nowrap">
                    МИССИЯ
                </h2>
            </div>
            
            <div class="flex-1 flex flex-col lg:flex-row gap-8">
                {#each missionData as mission, i}
                    <div class="w-full lg:w-1/3">
                        <div class="bg-white p-6 rounded-xl shadow-lg border-l-4 border-{mission.color}-500 hover:shadow-xl transition-shadow h-full flex flex-col">
                            <h3 class="text-2xl font-bold mb-4 text-{mission.color}-600 uppercase tracking-wider text-center">
                                {mission.title}
                            </h3>
                            <p class="text-lg text-gray-700 leading-relaxed text-center flex-grow">
                                {mission.description}
                            </p>
                        </div>
                    </div>
                {/each}
            </div>
        </div>
    </div>
</section>
