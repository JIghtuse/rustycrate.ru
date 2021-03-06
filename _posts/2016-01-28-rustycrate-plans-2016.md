---
title: Наши результаты и планы на 2016
categories: новости
author: Панков Михаил
excerpt: >
  Всем привет! В этой публикации я попробую описать состояние нашего сообщества и
  экосистемы, сформировавшейся вокруг него, а затем опишу области, которые, на мой
  взгляд, стоит развивать.

---

Всем привет! В этой публикации я попробую описать состояние нашего сообщества и
экосистемы, сформировавшейся вокруг него, а затем опишу области, которые, на мой
взгляд, стоит развивать.

Обсудить эти планы можно в комментариях к публикации.

Но сначала я хочу сказать спасибо всем участникам нашего сообщества — за работу,
за общение и за поддержку. Я рад, что не я один работаю над улучшением
сообщества. У нас очень дружелюбный народ в чате. Мы выросли до 150 человек за
пару месяцев. Продолжайте в том же духе — это много значит :)

Также прошу присылать Pull Requestʼы с исправлениями и дополнениями этой
публикации, если что-то не так.

А теперь к делу. Я рассмотрю результаты 2015-го и разные грани возможных
улучшений — и при этом, надеюсь, не напишу очень длинный текст. Я не буду сильно
вдаваться в подробности, поэтому если вы хотите узнать о чём-то больше — пишите
мне на [почту](http://rustycrate.ru/contacts.html) или в
[чате](https://gitter.im/ruRust/general).

# Результаты

За 2015-й год мы достигли хороших результатов. С нуля переведена книга, создано
сообщество, наш сайт, написано множество статей.

Вот некоторые цифры:

  * 20 участников сделали 932 коммита в репозиторий книги и отправили 243 Pull
    Requestʼа
  * это примерно
    [100 000 строк](https://github.com/ruRust/rust_book_ru/graphs/contributors)
    изменений
  * репозиторий книги получает больше 1000 просмотров от 250 уникальных
    посетителей за неделю
  * 16 участников сделали 253 коммита в репозиторий сайта
  * наш сайт получает примерно 800 уникальных посещений в сутки
  * в основном канале нашего чата 150 человек
  * нами и другими авторами написано 42 поста в хаб Rust на Хабрахабре —
    за неполный год, с момента выпуска 1.0

Объём проделанной работы огромен.

Дабы мы не забывали, зачем мы всё это делаем, я ещё раз пропишу наши цели.
Мы хотим, чтобы программисты знали и использовали Rust, их начальники одобряли
такой выбор, коллеги завидовали, а работодатели размещали вакансии с заветными
словами «разработчик на Rust». Не много, не мало. По совместительству, мы делаем
мир немножечко лучше.

Планов на будущее у нас ещё больше!

# Сообщество

## Общие задачи

Во всех наших проектах нужно написать руководство по внесению изменений
(`CONTRIBUTING.md`). Как собрать проект, как проверить изменения, как сделать
Pull Request, и как редактировать файлы прямо в браузере. Это необходимый
минимум того, что нужно людям, которые хотят работать с нами.

Далее в процессе рецензирование изменений — а поэтому короткий документ нужен
и про сервис Reviewable, который мы используем во всех проектах. Нужно описать
как рецензировать, как работать с замечаниями чтобы это было быстро и удобно.

Для упрощения вовлечения людей нужно завести тег «легко» и назначить его простым
задачам, которые подходят для новичков.

Помимо этого, основная наша площадка для общения на данный момент —
[чат-комната](https://gitter.im/ruRust/general) на Gitter. Сервис имеет
некоторые продвинутые возможности, о которых не все знают — про них стоит
рассказать.

## Книга

В книге 2 основных направления — полная
[синхронизация](https://github.com/ruRust/rust_book_ru/issues/3) текущей версии
с оригиналом и перевод [новой книги](https://github.com/rust-lang/book). Помимо
этого, есть инфраструктурная работа — например, переход на mdBook.

Также нужна система
[отслеживания](https://github.com/ruRust/rust_book_ru/issues/6) изменений
в оригинале, с тем чтобы было проще обновлять перевод. Эта задача — очень
глобальная, и здесь нужно взаимодействовать с Rust Core Team. В
[этой](https://internals.rust-lang.org/t/better-support-translations-for-the-book/3003)
и [этой](https://internals.rust-lang.org/t/translations-for-rust/3126) темах
идёт обсуждение процесса. В них стоит вникнуть, чтобы хорошо интегрироваться с
остальным сообществом.

## mdBook

[mdBook](https://github.com/azerupi/mdBook) — новая программа вёрстки книги из
Markdown-файлов. Она лучше существующего rustbook в нескольких аспектах, и на
неё в какой-то момент перейдёт оригинал. Поэтому нам тоже нужно смотреть на эту
часть инфраструктуры.

Здесь есть два особенно важных момента. Первый — нам нужна поддержка экспорта
книги в форматах для читалок и для печати — т. е. в EPUB, MOBI, PDF. Сейчас мы
используем Calibre, и с ним есть сложно решаемые проблемы
([1](https://github.com/ruRust/rust_book_ru/issues/8),
[2](https://github.com/ruRust/rust_book_ru/issues/9)). В то же время, эта
возможность довольно хорошо реализована
в [trpl-ebook](https://github.com/ruRust/trpl-ebook). Ссылка ведёт на форк
в нашей организации — я пробовал прогонять через trpl-ebook наш перевод
и обнаружил несколько необходимых изменений. @killercup, автор trpl-ebook,
справедливо отметил, что активная работа по версиям для читалок ведётся в самом
mdBook, поэтому нам надо будет участвовать в этом проекте. Помимо этого,
trpl-ebook не очень модульный и слабо подходит для внешнего использования —
сейчас он рассчитывает, что всё наполнение книги лежит прямо в том же
репозитории, а так же не полностью параметризован. Например, некоторые строки,
зависящие от языка книги, зашиты прямо в код.

Второй важный момент — в mdBook
[планируют](https://github.com/azerupi/mdBook/issues/5) интегрировать переводы.
Здесь тоже требуется наше участие.

Отмечу, что mdBook сам по себе — это программа на Rust. Она не запредельно
сложная, но представляет из себя реальный проект — поэтому это хороший вариант
для пробы своих сил в написании настоящего кода на Rust. Если вас пугает code
review на английском — мы можем это решить через отправку изменений сначала в
наш репозиторий. Тогда наше сообщество будет рецензировать ваш код, а дальше уже
мы будем отправлять Pull Requestʼы в исходный репозиторий.

К тому же есть на что ориентироваться в реализации — код trpl-ebook (это,
кстати, тоже программа на Rust) весьма мал и прост. Можно брать его код,
понимать что он делает, и реализовывать аналогичную функциональность в mdBook.
Поэтому ещё раз подчеркну — эта область отлично подходит для практического
участия в open source проекте, да ещё и на нашем любимом языке.

## Другие книги

Есть несколько других книг про Rust на английском — «Rustonomicon»
о небезопасном Rust, «The Little Book of Rust Macros» о макросах, и «Rust
by Example» — прагматичная книга, обучающая языку на примерах. У последней,
кстати, есть незаконченный [перевод](https://github.com/suhr/rust-by-example)
на русский. Эта область со временем тоже потребует нашего внимания, но сначала
нам совершенно точно стоит решить инфраструктурные вопросы.

## Сайт

В развитии сайта есть задачи для DevOps и фронтенд-разработчиков. Нам нужно
прикрутить систему сообщения об опечатках (возможно,
[Orphus](http://orphus.ru/)),
[типографику](https://github.com/ruRust/rustycrate.ru/issues/7),
[категории](https://github.com/ruRust/rustycrate.ru/issues/27),
[теги](https://github.com/ruRust/rustycrate.ru/issues/26),
и [поиск](https://github.com/ruRust/rustycrate.ru/issues/28). Сайт работает
на Jekyll и Twitter Bootstrap, легко собирается локально, и разворачивается
автоматически после принятия Pull Requestʼа. Поэтому если хотите
попрактиковаться в веб-разработке — можно заняться этим. Здесь задачи более
открытые и требующие большей инициативы, но мы готовы помогать желающим заняться
этим.

Помимо разработки, есть задачи по наполнению сайта статьями. Нам нужны
руководства по лучшим практикам
[ведения проекта](https://github.com/ruRust/rustycrate.ru/issues/45), настройке
[Continuous Integration](https://github.com/ruRust/rustycrate.ru/issues/40),
[кросс-компиляции](https://github.com/ruRust/rustycrate.ru/issues/38), менеджеру
проектов [Cargo](https://github.com/ruRust/rustycrate.ru/issues/37). Нам нужен
раздел [ссылок](https://github.com/ruRust/rustycrate.ru/issues/68)
и [каталог проектов](https://github.com/ruRust/rustycrate.ru/issues/69) —
подобный тому, который можно найти в конце этой публикации.

Хочу напомнить, что у нас есть полностью функциональный
[форум](http://forum.rustycrate.ru/) на платформе Discourse — если вы любите
асинхронное общение или у вас большой вопрос, пишите сюда. Здесь информацию
легче искать и она более доступна для тех, кто сталкивается с похожими
проблемами.

<hr/>

В заключение этой части, если вы или ваши знакомые хотят поучаствовать в активно
развивающемся проекте, их есть у нас — много и на любой вкус. Мы рады принять
изменения от любых разработчиков, поэтому не стесняйтесь задавать вопросы,
предлагать идеи, и, конечно, присылать Pull Requestʼы. Это отличный способ
получить ценный опыт, заработать репутацию в open source сообществе, и повод
добавить строчку в резюме.

# Встреча

Я очень хочу организовать встречу для разработчиков на Rust. Ориентировочно в
мае — спустя год после выпуска версии 1.0. Пока не могу сказать ничего ни о
месте, ни о формате — всё совсем не определено. Если у вас есть идеи,
предложения, или вы знаете людей, которые могут помочь — пишите
[на форум](http://forum.rustycrate.ru/t/vstrecha-dlya-razrabotchikov/56) или
лично [мне](http://rustycrate.ru/contacts.html). Я буду очень рад любой помощи в
организации этого события.

# Экосистема

Также хочу рассказать об очень важной части нашего сообщества — об экосистеме.
Мы не только разговариваем о Rust, мы пишем код на Rust.
[@listochkin](https://github.com/listochkin) развернул серверный компонент на
Rust. Я экспериментально применяю Rust на своей основной работе. И, конечно,
участники нашего сообщества являются авторами библиотек. Некоторые из них —
де-факто стандартные; у них тысячи загрузок. Приведу неполный список
(в алфавитном порядке):

  * [@blackbeam](https://github.com/blackbeam)
      * [crc16](https://crates.io/crates/crc16/) — реализация CRC16
      * [marc](https://crates.io/crates/marc/) — библиотека для чтения и
        создания библиографии в формате MARC 21
      * [mysql](https://crates.io/crates/mysql/) — клиентская библиотека MySQL
      * [named-pipe](https://crates.io/crates/named_pipe/) — обёртка для
        асинхронного ввода-вывода в именованные каналы Windows
      * [rabbit](https://crates.io/crates/rabbit/) — реализация Rabbit Stream
        Cipher Algorithmс поддержкой окружения без стандартной библиотеки
        (no_std)
  * [@defuz](https://github.com/defuz/)
      * [onig](https://crates.io/crates/onig) — обёртка для библиотеки
        регулярных выражений oniguruma, поддерживающей различные кодировки
      * [weakjson](https://crates.io/crates/weakjson/) — библиотека для разбора
        нестандартного JSON, который вы можете встретить на просторах интернета
  * [@kstep](https://github.com/kstep)
      * [cronparse](https://crates.io/crates/cronparse/) — парсер файлов crontab
      * [kernlog](https://crates.io/crates/kernlog/) — реализация
        низкоуровневого журналирования в `/dev/kmsg`
      * [mpd](https://crates.io/crates/mpd/) — клиентская библиотека для MPD
        (music player daemon)
      * [pb](https://crates.io/crates/pb/) — клиент REST API сервиса
        PUSH-уведомлений [Pushbullet](https://www.pushbullet.com/)
      * [vkrs](https://crates.io/crates/vkrs/) — клиент API Вконтакте
      * …и другие
  * [@mkpankov](https://github.com/mkpankov/)
      * [bread](https://crates.io/crates/bread/) — библиотека для
        форматированного вывода в терминал (цвет, стиль и т. д.), принимающая
        разметку прямо в выводимой строке
  * [@netvl](https://github.com/netvl/)
      * [ejdb.rs](https://crates.io/crates/ejdb) — обёртка для EJDB,
        встраиваемой базе данных на JSON
      * [immeta](https://crates.io/crates/immeta) — библиотека разбора
        метаданных изображений
      * [mpfr.rs](https://crates.io/crates/mpfr/) — высокоуровневая обёртка для
        MPFR, библиотеки для вычислений с произвольной точностью
      * [xml-rs](https://crates.io/crates/xml-rs/) — библиотека для работы с
        XML, полностью на Rust
  * [@SCareAngel](https://github.com/SCareAngel)
      * [functional](https://crates.io/crates/functional/) — типажи для
        реализации функционального программирования на Rust (привет, монады!)
      * [future](https://crates.io/crates/future/) — разделяемый асинхронный
        результат вычислений (continuation, похоже на std: future из C++)
      * [pixel](https://crates.io/crates/pixel/) — библиотека для конвертации и
        смешивания (blending) цветов
  * [@Vinatorul](https://github.com/Vinatorul)
      * [clap](https://crates.io/crates/clap) — библиотека разбора аргументов
        командной строки
  * [@zummenix](https://github.com/zummenix)
      * [expectest](https://crates.io/crates/expectest/) — библиотека для
        реализации модульных тестов на Rust

По-моему, неплохо для нашего небольшого, но сплочённого сообщества — особенно
учитывая, что с выпуска 1.0 не прошло и года.

Вы можете задавать авторам вопросы или поучаствовать в этих проектах — без
языкового барьера. Просто приходите к нам в
[чат](https://gitter.im/ruRust/general).

Хочу также выделить один крупный проект приложения на Rust, которое явно будет
полезно самим разработчикам — редактор
[sublimate](https://github.com/defuz/sublimate) от @defuz. Проект довольно
амбициозен — реализация аналога Sublime Text 3 на Rust и с полностью открытым
кодом. Разработка идёт хорошими темпами, и это ещё один шанс поучаствовать в
реальном проекте и получить опыт программирования на языке, востребованность
которого будет экспоненциально расти в ближайшие годы.

# Разнообразные материалы

Упомяну также известные мне доклады и статьи о Rust — чтобы было на что
опираться, рассказывая коллегам и начальникам о нашем замечательном языке.

  * Почему Rust стоит вашего внимания: мой
    [доклад](http://michaelpankov.com/why-rust-matters.pdf),
    [видео выступления](https://youtu.be/slnQBoxsHPU)
  * Rust — лучше, чем C++: немного устаревшее
    [видео выступления](https://events.yandex.ru/lib/talks/1978/) Степана
    Кольцова из Яндекса
  * Rust Launch Party Kyiv + Lviv + Friends:
    [запись](https://youtu.be/k7amezcV0AI) Hangouts в день выпуска 1.0
  * Наш блог [rustycrate.ru](http://rustycrate.ru/)
      * [IDE](http://rustycrate.ru/%D1%80%D1%83%D0%BA%D0%BE%D0%B2%D0%BE%D0%B4%D1%81%D1%82%D0%B2%D0%B0/2015/12/04/ide-for-rust.html)
        для Rust
      * Статьи о времени жизни в Rust:
        [часть 1](http://rustycrate.ru/%D0%BE%D0%B1%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5/2015/11/14/lifetime-part1.html),
        [часть 2](http://rustycrate.ru/%D0%BE%D0%B1%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5/2015/11/14/lifetime-part2.html)
  * Хабрахабр, [хаб «Rust»](https://habrahabr.ru/hub/rust/), в частности:
      * [Начинаем](https://habrahabr.ru/post/270137/) использовать Rust
      * Обработка [ошибок](https://habrahabr.ru/post/270371/) в Rust
      * Цикл статей о реализации
        [REST-сервера](https://habrahabr.ru/post/269903/)
      * [Сравниваем](https://habrahabr.ru/post/272681/) Swift и Rust
      * Пишем свой упрощённый [OpenGL](https://habrahabr.ru/post/262235/)
        на Rust
      * Rust в деталях: пишем масштабируемый чат с нуля,
        [часть 1](https://habrahabr.ru/post/268609/)
      * Rust в [2016 году](https://habrahabr.ru/post/274757/)

<hr/>

На этом, пожалуй, всё. Рассказывайте о нас знакомым, убеждайте коллег, что Rust
стоит изучения, поведайте начальнику, что с Rust сервера не упадут в продакшене.
Успехов и до новых встреч!
