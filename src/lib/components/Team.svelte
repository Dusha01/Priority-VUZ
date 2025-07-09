<script>
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

<section id="team" class="py-24 bg-gray-100">
    <div class="container mx-auto px-4 h-full">
        <div class="flex flex-col lg:flex-row gap-8 lg:gap-16 items-stretch h-full">
            <div class="lg:w-24 flex justify-center items-center">
                <h2 class="text-4xl font-bold writing-mode-vertical lg:writing-mode-vertical rotate-270 text-gray-800 tracking-wider whitespace-nowrap">
                    КОМАНДА
                </h2>
            </div>

            <div class="flex-1 grid grid-cols-2 md:grid-cols-3 lg:grid-cols-5 gap-6">
                {#each teamMembers as member}
                    <div class="bg-white rounded-lg shadow-md overflow-hidden hover:shadow-lg transform hover:scale-105 transition-all duration-200">
                        <div class="flex justify-center">
                            <img 
                                src={member.imageUrl} 
                                alt={member.name} 
                                class="w-40 h-36 object-cover object-center rounded-lg mt-4" 
                            />
                        </div>
                        <div class="p-4">
                            <h3 class="text-lg font-semibold text-gray-800">{member.name}</h3>
                            <p class="text-sm text-gray-600">{member.title}</p>
                        </div>
                    </div>
                {/each}
            </div>
        </div>
    </div>
</section>
