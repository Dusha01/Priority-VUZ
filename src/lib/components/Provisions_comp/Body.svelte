<script lang="ts">
    interface Document {
      id: string;
      number: string;
      title: string;
      description: string;
      filePath: string;
    }
  
    const documents: Document[] = [
      {
        id: "08-12.1-24",
        number: "П 08-12.1-24",
        title: "О проекте «Международная транспортная академия»",
        description: "в рамках реализации программы стратегического академического лидерства «Приоритет-2030»",
        filePath: "https://dvgups.ru/prioritet-2030-dalnij-vostok/img/documents/P%2008-12.1-24.pdf"
      },
      {
        id: "08-5.1.1-24",
        number: "П 08-5.1.1-24",
        title: "О проекте «Цифровые электрические системы и инфраструктура»",
        description: "в рамках реализации программы стратегического академического лидерства «Приоритет-2030»",
        filePath: "https://dvgups.ru/prioritet-2030-dalnij-vostok/img/documents/%D0%9F%2008-5.1.1-24.pdf"
      },
      {
        id: "08-1.1.1-24",
        number: "П 08-1.1.1-24",
        title: "О проекте «Лаборатория управления надёжностью технических систем в условиях работы в Северной и Арктической зонах»",
        description: "в рамках реализации программы стратегического академического лидерства «Приоритет-2030»",
        filePath: "https://dvgups.ru/prioritet-2030-dalnij-vostok/img/documents/P%2008-1.1.1-24.pdf"
      },
      {
        id: "08-13.1-24",
        number: "П 08-13.1-24",
        title: "О проекте «Развитие кадрового потенциала авиационных предприятий ДФО»",
        description: "в рамках реализации программы стратегического академического лидерства «Приоритет-2030»",
        filePath: "https://dvgups.ru/prioritet-2030-dalnij-vostok/img/documents/%D0%9F%2008-13.1-24.pdf"
      },
      {
        id: "11-36-24",
        number: "П 11-36-24",
        title: "О проекте «Галактика спорта ДВГУПС»",
        description: "в рамках реализации программы стратегического академического лидерства «Приоритет-2030»",
        filePath: "https://dvgups.ru/prioritet-2030-dalnij-vostok/img/documents/%D0%9F%2011-36-24.pdf"
      },
      {
        id: "10-2.1.1-24",
        number: "П 10-2.1.1-24",
        title: "О проекте «Лаборатория маркетинговых исследований транспортного комплекса Дальневосточного региона»",
        description: "в рамках реализации программы стратегического академического лидерства «Приоритет-2030»",
        filePath: "https://dvgups.ru/prioritet-2030-dalnij-vostok/img/documents/%D0%9F%2010-2.1.1-24.pdf"
      },
      {
        id: "08-2.5-24",
        number: "П 08-2.5-24",
        title: "О проекте «IT-лаборатория аналитики и прогнозирования транспортных процессов и логистики»",
        description: "в рамках реализации программы стратегического академического лидерства «Приоритет-2030»",
        filePath: "https://dvgups.ru/prioritet-2030-dalnij-vostok/img/documents/%D0%9F%2008-2.5-24.pdf"
      },
      {
        id: "08-2.6-24",
        number: "П 08-2.6-24",
        title: "О проекте «Передовая инженерная школа Г.М. Фадеева»",
        description: "в рамках реализации программы стратегического академического лидерства «Приоритет-2030»",
        filePath: "https://dvgups.ru/prioritet-2030-dalnij-vostok/img/documents/%D0%9F%2008-2.6-24.pdf"
      },
      {
        id: "08-7.5.1-24",
        number: "П 08-7.5.1-24",
        title: "О проекте «Научно-образовательный центр «Аддитивные технологии»»",
        description: "в рамках реализации программы стратегического академического лидерства «Приоритет-2030»",
        filePath: "https://dvgups.ru/prioritet-2030-dalnij-vostok/img/documents/%D0%9F%2008-7.5.1-24.pdf"
      },
      {
        id: "10-15-24",
        number: "П 10-15-24",
        title: "О проекте «Комплексная лаборатория геотехнического строительства на промерзающих, многолетнемерзлых и оттаивающих грунтах в Дальневосточном Федеральном Округе и Арктике»",
        description: "в рамках реализации программы стратегического академического лидерства «Приоритет-2030»",
        filePath: "https://dvgups.ru/prioritet-2030-dalnij-vostok/img/documents/%D0%9F%2010-15-24.pdf"
      },
      {
        id: "07-17.1-24",
        number: "П 07-17.1-24",
        title: "О проекте «МЕДИАКЛАСТЕР»",
        description: "в рамках реализации программы стратегического академического лидерства «Приоритет-2030»",
        filePath: "https://dvgups.ru/prioritet-2030-dalnij-vostok/img/documents/%D0%9F%D0%BE%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5%20%D0%94%D0%92%D0%93%D0%A3%D0%9F%D0%A1%20%D0%9F%2007-17.1-24.pdf"
      },
      {
        id: "10-14-24",
        number: "П 10-14-24",
        title: "О проекте «Университет кадровых трансформаций»",
        description: "в рамках реализации программы стратегического академического лидерства «Приоритет-2030»",
        filePath: "https://dvgups.ru/prioritet-2030-dalnij-vostok/img/documents/%D0%9F%D0%BE%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5%20%D0%94%D0%92%D0%93%D0%A3%D0%9F%D0%A1%20%D0%9F%2010-14-24.pdf"
      }
    ];
  </script>
  
  <section class="py-12 bg-gray-50">
    <div class="container mx-auto px-4 sm:px-6">
        <div class="mb-8">
            <h2 class="text-3xl font-bold text-gray-800">Положения</h2>
        </div>
  
        <div class="space-y-6">
            {#each documents as document}
                <div class="group">
                    <a href={document.filePath} id={document.id} target="_blank" rel="noopener noreferrer" class="block p-6 bg-white rounded-lg shadow-sm hover:shadow-md transition-shadow duration-300">
                        <h3 class="text-xl font-semibold text-blue-600 mb-2">
                            Положение ДВГУПС {document.number}
                        </h3>
                        <p class="text-lg font-medium text-gray-800 mb-1">
                            {document.title}
                        </p>
                        <p class="text-gray-600">
                            {document.description}
                        </p>
                    </a>
                    {#if document.id !== documents[documents.length - 1].id}
                        <hr class="my-6 border-gray-200" />
                    {/if}
                </div>
            {/each}
        </div>
    </div>
</section>