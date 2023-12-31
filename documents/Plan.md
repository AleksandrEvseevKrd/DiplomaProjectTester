## Перечень автоматизируемых сценариев
 Валидные данные:
1.	Поле «Номер карты»: цифровые символы, 16 шт., в формате **** **** **** ****.
2.	Поле «Месяц»: 01-12, но не ранее текущего месяца в случае, если указан текущий год.
3.	Поле «Год»: последние 2 цифры года, но не раньше текущего, и не более 5 лет от текущего.
4.	Поле «Владелец»: латиница, использование верхнего регистра, пробела, дефиса
5.	Поле «CVC/CVV»: числовое значение из 3-х цифр.

### Позитивные сценарии:
1.	Оплата тура по карте со статусом «APPROVED»
Номер карты: 4444 4444 4444 4441. Остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: появление всплывающего окна «Операция одобрена Банком», запись со статусом «APPROVED» в базе данных.
2.	Кредит на тур по карте со статусом «APPROVED»
Номер карты: 4444 4444 4444 4441. Остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: появление всплывающего окна «Операция одобрена Банком», запись со статусом «APPROVED» в базе данных.
3.	Оплата тура по карте со статусом «DECLINED»
Номер карты: 4444 4444 4444 4442. Остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: появление всплывающего окна «Ошибка! Банк отказал в проведении операции», запись со статусом «DECLINED» в базе данных.
4.	Кредит на тур по карте со статусом «DECLINED»
Номер карты: 4444 4444 4444 4442. Остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: появление всплывающего окна «Ошибка! Банк отказал в проведении операции», запись со статусом «DECLINED» в базе данных.

### Негативные сценарии:
1.	Оплата тура по несуществующей карте:
Номер карты: 4444 4444 4444 4444. Остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: появление всплывающего окна «Ошибка! Банк отказал в проведении операции», отсутствие записи в базе данных.
2.	Кредит на тур по несуществующей карте:
Номер карты: 4444 4444 4444 4444. Остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: появление всплывающего окна «Ошибка! Банк отказал в проведении операции», отсутствие записи в базе данных.
3.	Оплата тура по карте с невалидными данными:
Номер карты: 4444 4444 4444 444. Остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: под полем «Номер карты» появилось сообщение об ошибке «Неверный формат», отсутствие записи в базе данных.
4.	Кредит на тур по карте с невалидными данными:
Номер карты: 4444 4444 4444 444. Остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: под полем «Номер карты» появилось сообщение об ошибке «Неверный формат», отсутствие записи в базе данных.
5.	Оплата тура по карте с истекшим сроком действия:
Номер карты: 4444 4444 4444 4441. В поле «Месяц» указать предыдущий месяц от текущего, остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: под полем «Месяц» появилось сообщение об ошибке «Неверно указан срок действия карты», отсутствие записи в базе данных.
6.	Кредит на тур по карте с истекшим сроком действия:
Номер карты: 4444 4444 4444 4441. В поле «Месяц» указать предыдущий месяц от текущего, остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: под полем «Месяц» появилось сообщение об ошибке «Неверно указан срок действия карты», отсутствие записи в базе данных.
7.	Оплата тура по карте с невалидным значением в поле «Месяц»:
Номер карты: 4444 4444 4444 4441. В поле «Месяц» указать 00, остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: под полем «Месяц» появилось сообщение об ошибке «Неверно указан срок действия карты», отсутствие записи в базе данных.
8.	Кредит на тур по карте с невалидным значением в поле «Месяц»:
Номер карты: 4444 4444 4444 4441. В поле «Месяц» указать 00, остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: под полем «Месяц» появилось сообщение об ошибке «Неверно указан срок действия карты», отсутствие записи в базе данных.
9.	Оплата тура по карте с незаполненным полем «Месяц»:
Номер карты: 4444 4444 4444 4441. Поле «Месяц» оставить незаполненным, остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: под полем «Месяц» появилось сообщение об ошибке «Неверный формат», отсутствие записи в базе данных.
10.	Кредит на тур по карте с незаполненным полем «Месяц»:
Номер карты: 4444 4444 4444 4441. Поле «Месяц» оставить незаполненным, остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: под полем «Месяц» появилось сообщение об ошибке «Неверный формат», отсутствие записи в базе данных.
11.	Оплата тура по карте с истекшим сроком действия:
Номер карты: 4444 4444 4444 4441. В поле «Год» указать предыдущий год от текущего, остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: под полем «Год» появилось сообщение об ошибке «Неверно указан срок действия карты», отсутствие записи в базе данных.
12.	Кредит на тур по карте с истекшим сроком действия:
Номер карты: 4444 4444 4444 4441. В поле «Год» указать предыдущий год от текущего, остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: под полем «Год» появилось сообщение об ошибке «Неверно указан срок действия карты», отсутствие записи в базе данных.
13.	Оплата тура по карте с невалидным значением в поле «Год»:
Номер карты: 4444 4444 4444 4441. В поле «Год» указать значение +5 лет от текущего года, остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: под полем «Год» появилось сообщение об ошибке «Неверно указан срок действия карты», отсутствие записи в базе данных.
14.	Кредит на тур по карте с невалидным значением в поле «Год»:
Номер карты: 4444 4444 4444 4441. В поле «Год» указать значение +5 лет от текущего года, остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: под полем «Год» появилось сообщение об ошибке «Неверно указан срок действия карты», отсутствие записи в базе данных.
15.	Оплата тура по карте с незаполненным полем «Год»:
Номер карты: 4444 4444 4444 4441. Поле «Год» оставить незаполненным, остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: под полем «Год» появилось сообщение об ошибке «Неверный формат», отсутствие записи в базе данных.
16.	Кредит на тур по карте с незаполненным полем «Год»:
Номер карты: 4444 4444 4444 4441. Поле «Год» оставить незаполненным, остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: под полем «Год» появилось сообщение об ошибке «Неверный формат», отсутствие записи в базе данных.
17.	Оплата тура по карте с невалидным значением в поле «Владелец»:
Номер карты: 4444 4444 4444 4441. В поле «Владелец» ввести цифры, остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: под полем «Владелец» появилось сообщение об ошибке «Неверный формат», отсутствие записи в базе данных.
18.	Кредит на тур по карте с невалидным значением в поле «Владелец»:
Номер карты: 4444 4444 4444 4441. В поле «Владелец» ввести цифры, спец.символы, остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: под полем «Владелец» появилось сообщение об ошибке «Неверный формат», отсутствие записи в базе данных.
19.	Оплата тура по карте с незаполненным полем «Владелец»: 
Номер карты: 4444 4444 4444 4441. Поле «Владелец» оставить незаполненным, остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: под полем «Владелец» появилось сообщение об ошибке «Поле обязательно для заполнения», отсутствие записи в базе данных.
20.	Кредит на тур по карте с незаполненным полем «Владелец»: 
Номер карты: 4444 4444 4444 4441. Поле «Владелец» оставить незаполненным, остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: под полем «Владелец» появилось сообщение об ошибке «Поле обязательно для заполнения», отсутствие записи в базе данных.
21.	Оплата тура по карте с невалидным значением в поле «CVC/CVV» (ввод 1-й цифры):
Номер карты: 4444 4444 4444 4441. В поле «CVC/CVV» ввести 1, остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: под полем «CVC/CVV» появилось сообщение об ошибке «Неверный формат», отсутствие записи в базе данных.
22.	Кредит на тур по карте с невалидным значением в поле «CVC/CVV» (ввод 1-й цифры):
Номер карты: 4444 4444 4444 4441. В поле «CVC/CVV» ввести 1, остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: под полем «CVC/CVV» появилось сообщение об ошибке «Неверный формат», отсутствие записи в базе данных.
23.	Оплата тура по карте с невалидным значением в поле «CVC/CVV» (ввод 2-х цифр):
Номер карты: 4444 4444 4444 4441. В поле «CVC/CVV» ввести 12, остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: под полем «CVC/CVV» появилось сообщение об ошибке «Неверный формат», отсутствие записи в базе данных.
24.	Кредит на тур по карте с невалидным значением в поле «CVC/CVV» (ввод 2-х цифр):
Номер карты: 4444 4444 4444 4441. В поле «CVC/CVV» ввести 12, остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: под полем «CVC/CVV» появилось сообщение об ошибке «Неверный формат», отсутствие записи в базе данных.
25.	Оплата тура по карте с незаполненным полем «CVC/CVV»:
Номер карты: 4444 4444 4444 4441. Поле «CVC/CVV» оставить незаполненным, остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: под полем «CVC/CVV» появилось сообщение об ошибке «Неверный формат», отсутствие записи в базе данных.
26.	Кредит на тур по карте с незаполненным полем «CVC/CVV»:
Номер карты: 4444 4444 4444 4441. Поле «CVC/CVV» оставить незаполненным, остальные поля заполнены валидными данными. Нажать кнопку «Продолжить». Ожидаемый результат: под полем «CVC/CVV» появилось сообщение об ошибке «Неверный формат», отсутствие записи в базе данных.
27.	 Оплата тура по карте с незаполненными полями:
Оставить все поля незаполненными. Нажать кнопку «Продолжить». Ожидаемый результат: под всеми полями появилось сообщение об ошибке «Неверный формат», отсутствие записи в базе данных.
28.	 Кредит на тур по карте с незаполненными данными:
Оставить все поля незаполненными. Нажать кнопку «Продолжить». Ожидаемый результат: под всеми полями появилось сообщение об ошибке «Неверный формат», отсутствие записи в базе данных.

## Перечень используемых инструментов с обоснованием выбора.
1.	Среда разработки - IntelliJ IDEA – это интегрированная среда разработки (комплекс программных средств, который используется для написания, исполнения, отладки и оптимизации кода). Отличается обширным набором инструментов для рефакторинга (перепроектирования) и оптимизации кода.
2.	Язык программирования: Java JDK 11 - имеет набор готового ПО для разработки и запуска приложений.
3.	Система автоматической сборки: Gradle - преимущества:
* Код на Gradle проще и меньше, разница заметна при реализации сборок с большим числом зависимостей.
* Благодаря использованию общих принципов проектирования Gradle позволяет создать удобный, понятный и быстро реализуемый проект.
* Проработанный API упрощает отслеживание и настройку конфигурации сборки, контроль ее исполнения.
* Система совместима с задачами Ant, инфраструктурой репозитория (сетевого хранилища) Maven и lvy, где можно опубликовать и получить зависимые компоненты. Есть также конвертеры для превращения Maven pom.xml в скрипт Gradle.
* Gradle легко приспосабливается к любой структуре, благодаря чему можно переносить с него и на него проекты, разработанные для других систем сборок.
* Gradle Wrapper – эта опция разрешает реализацию сборок, созданных в Gradle, на машинах, где система не установлена. Это упрощает непрерывную интеграцию серверов.
* Гибкость языка - Groove, в отличие от жестко заданных XML-иерархий Ant и Maven, дает разработчику больше вариантов действия, позволяет оптимизировать проект.
4.	Тестовая среда: JUnit5 — это платформа для написания и запуска авто-тестов в Java. Она широко используется в сообществе разработчиков и имеет обширную поддержку. JUnit обладает простым и понятным синтаксисом, а также предоставляет множество возможностей для проверки функциональности кода.
5.	Selenide (для UI тестирования)- библиотека для написания лаконичных и стабильных UI тестов с открытым исходным кодом.
6.	Rest Assured (для API тестирования) - java-библиотека для тестирования REST API, позволяет автоматизировать тестирование GET и POST запросов.
7.	Lombok - плагин для минимизации строк кода за счет аннотаций позволяет оптимизировать код автотестов, добавляет в Java новые «ключевые слова» и превращает аннотации в Java-код, уменьшая усилия на разработку и обеспечивая некоторую дополнительную функциональность.
8.	JavaFaker - библиотека для генерации случайных тестовых данных.
9.	Docker Desktop — это платформа контейнеризации с открытым исходным кодом. для развертывания контейнера с базой данных MySQL.
10.	Allure - фреймворк для создания отчетов о тестировании, для наглядного отображения прохождения тестов и ошибок (более сложные системы репортинга будут излишни).
11.	Git и GitHub - для хранения кода. Git достаточно прост и удобен для управления исходным кодом, очень распространенная система контроля версий, поэтому достаточно хорошо взаимодействует с различными ОС. GitHub специализированный веб-сервис с удобным интерфейсом, интегрирован с Git.

## Перечень и описание возможных рисков при автоматизации:
* Сложность в настройке тестовой среды.
* Проблемы с Docker на Windows 10.
* Проблемы с одновременным использованием MySql и Postgres.
* Проблемы с запуском SUT с различными параметрами.
* Реальная система и реальные данные скорее всего будут отличаться от SUT и тестовых данных, и автоматизация тестирования может оказаться бесполезной 
* Использование сторонних библиотек и фреймворков может увеличивать риск возникновения технических проблем

## Интервальная оценка с учетом рисков в часах:
1.	Разработка автотестов: 55 часов (с учетом возможных рисков +5 часов).
2. Подготовка тестового окружения: 15 часов (с учетом возможных рисков +5 часов).
3. Запуск и отладка автотестов: 25 часов (с учетом возможных рисков +8 часов).
4. Обновление и поддержка автотестов: 10 часов (с учетом возможных рисков +5 часов).
* Итого: 105 часов (с учетом возможных рисков +23 часов).

## План сдачи работ:
1.	Разработка автотестов: Завершение 30.11.2023
2.	Подготовка тестового окружения: Завершение 23.11.2023
3.	Запуск и отладка автотестов: Завершение 01.12.2023
4.	Обновление и поддержка автотестов: Операционная работа, продолжается в течение всего периода тестирования.
5.	Результаты прогона автотестов: Формирование отчетов по результатам прогона каждую неделю.
Примечание: Данные сроки могут быть скорректированы в зависимости от реального прогресса работы и возникновения дополнительных рисков.
