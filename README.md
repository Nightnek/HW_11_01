# 11-1 Стасенко Григорий Домашнее задание к занятию «Базы данных, их типы» 11-1

## Задание 1. СУБД
Кейс
Крупная строительная компания, которая также занимается проектированием и девелопментом, решила создать правильную архитектуру для работы с данными. Ниже представлены задачи, которые необходимо решить для каждой предметной области.

Какие типы СУБД, на ваш взгляд, лучше всего подойдут для решения этих задач и почему?

1.1. Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков. СУБД должна гарантировать целостность и чёткую структуру данных.

````
В данном случае, подойдет клиент-серверная реляцонная СУБД.
````

1.1.* Хеширование стало занимать длительно время, какое API можно использовать для ускорения работы?

````
Если хеширование занимает слишком много времени, можно использовать специализированные алгоритмы хеширования или библиотеки, которые оптимизированы для быстрой работы с хешами. Вот несколько API и библиотек, которые могут помочь ускорить процесс хеширования:

OpenSSL: Это популярная библиотека, которая предоставляет широкий спектр криптографических функций, включая хеширование. Она оптимизирована для высокой производительности и может быть использована для ускорения хеширования.
Intel IPP (Integrated Performance Primitives): Это набор оптимизированных функций для выполнения различных операций, включая хеширование. Он предоставляет оптимизированные реализации алгоритмов хеширования, которые могут значительно ускорить процесс.
Google's CityHash: Это хорошо известная библиотека хеширования, разработанная Google. Она оптимизирована для работы с большими объемами данных и может быть полезна, если вам нужно хешировать большие файлы или потоки данных.
xxHash: Это быстрый хеш-алгоритм, который обеспечивает высокую скорость хеширования. Он может быть полезен, если вам нужно быстро хешировать большие объемы данных.
MurmurHash: Это еще один быстрый хеш-алгоритм, который обеспечивает хорошую скорость хеширования. Он также может быть полезен для ускорения процесса хеширования.
````

1.2. Под каждый девелоперский проект создаётся отдельный лендинг, и все данные по лидам стекаются в CRM к маркетологам и менеджерам по продажам. Какой тип СУБД лучше использовать для лендингов и для CRM? СУБД должны быть гибкими и быстрыми.

````
Для данных задач лучше подойдут NoSQL системы.
Для лендингов MongoDB, а для CRM - Apache Cassandra.
NoSQL базы данных обеспечивают гибкость, быструю обработку данных и масштабируемость, что делает их хорошим выбором для лендингов и CRM систем.
````

1.2.* Можно ли эту задачу закрыть одной СУБД? И если да, то какой именно СУБД и какой реализацией?

````
Для решения данной задачи с помощью одной СУБД может подойти Apache Cassandra, так как она обеспечивает возможность создания разных таблиц для разных типов данных, что позволяет эффективно хранить и обрабатывать данные из разных источников
````

1.3. Отдел контроля качества решил создать базу по корпоративным нормам и правилам, обучающему материалу и так далее, сформированную согласно структуре компании. СУБД должна иметь простую и понятную структуру.

````
Для данной задачи подойдет реляционная SQL СУБД.
Например PostgreSQL или MySQL.

````

1.3.* Можно ли под эту задачу использовать уже существующую СУБД из задач выше и если да, то как лучше это реализовать?

````
Можно, если используется реляционная SQL СУБД, такая как, например PostgreSQL или MySQL.
Лучше всего, в таком случае, создать отдельную схему внутри существующей БД.
````

1.4. Департамент логистики нуждается в решении задач по быстрому формированию маршрутов доставки материалов по объектам и распределению курьеров по маршрутам с доставкой документов. СУБД должна уметь быстро работать со связями.

````
Для данной задачи подойдет графовая СУБД, например:
InfiniteGraph
InfoGrid
Neo4j
````

1.4.* Можно ли к этой СУБД подключить отдел закупок или для них лучше сформировать свою СУБД в связке с СУБД логистов?

````
В случае, если отдел закупок имеет общие данные или взаимосвязанные задачи с логистами, и нет отличающихся требований по хранению данных, к этой СУБД можно подключить логистов.
Так как графовые системы обладают гибкостью в моделировании, проблем с этим не возникнет.
````

1.5.* Можно ли все перечисленные выше задачи решить, используя одну СУБД? Если да, то какую именно?

````
Да, все перечисленные выше задачи можно решить, используя гибкую и мощную мульти-модельную базу данных, такую как ArangoDB
````


---

## Задание 2. Транзакции
2.1. Пользователь пополняет баланс счёта телефона, распишите пошагово, какие действия должны произойти для того, чтобы транзакция завершилась успешно. Ориентируйтесь на шесть действий.

````
1) проверяется наличие и достаточность средств на счете, с которого идет пополнение
2) проверяется доступность счета пополнения в платежной системе
3) производится резервирование средств для перевода
4) передается запрос на перевод средств в платежную систему
5) платежная ситема передает запрос на пополнение счета телефона
6) платежная ситема передает запрос на списание денежных средств со счета пользователя
````

2.1.* Какие действия должны произойти, если пополнение счёта телефона происходило бы через автоплатёж?

````

````
 
## Задание 3. SQL vs NoSQL
3.1. Напишите пять преимуществ SQL-систем по отношению к NoSQL.

````
Стандартный язык запросов SQL
Хорошая структурируемость
Простота использования
Изменяемая схема
Совместимость с популярными языками программирования
````

---
3.1.* Какие, на ваш взгляд, преимущества у NewSQL систем перед SQL и NoSQL.

````
В NewSQL не используется ресурсоемкий буферный пул, поскольку база данных целиком находится в основной памяти
устраняет потребность в краткосрочных блокировках данных, поскольку система исполняется на сервере строго в виде одиночного потока
«дорогостоящие» операции восстановления исключаются за засчет применения дополнительных серверов для тиражирования и переключения нагрузки при отказе
````

---

## Задание 4. Кластеры
Необходимо производить большое количество вычислений при работе с огромным количеством данных, под эту задачу выделено 1000 машин.
На основе какого критерия будете выбирать тип СУБД и какая модель распределённых вычислений здесь справится лучше всего и почему?

````
Критерии выбора СУБД: производительность, надёжность, особенность архетектуры и функциональные возможности, контроль работы системы. Модель для СУБД "Клиент-сервер"- вычислительная или сетевая архитектура, в которой задания или сетевая нагрузка распределенны между поставщиками услуг, называемыми серверами и заказчиками услуг, называемыми клиентами. Поскольку одна программа-сервер может выполнять запросы от множества программ-клиентов, её размещают на специально выделенной вычислительной машине, настроенной особым образом, как правило, совместно с другими программами-серверами, поэтому производительность этой машины должна быть высокой.
````

---
