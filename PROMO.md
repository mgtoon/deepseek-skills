# Продвижение репозитория

Короткий план и готовые тексты. Задача — не «много звёзд», а попасть к тем, кто уже ругается на шаблонные сайты от LLM.

## Позиционирование

Одна строка для описания: **«Промпт-скилы для DeepSeek: бриф перед вёрсткой и 10 проходов проверки, чтобы не было шаблонных сайтов и кода-пустышек»**.

Три варианта подачи:

- для разработчиков: «Правила, которые заставляют модель сначала спросить про дизайн, а потом проверять свою работу десять раз».
- для дизайнеров: «Почему все сайты от ИИ одинаковые и как это чинится промптом».
- для всех: «Скопировал, вставил первым сообщением — модель перестала делать фиолетовые градиенты».

## Куда идти

| Площадка | Аудитория | Формат | Шанс |
|---|---|---|---|
| GitHub topics + поиск | свои | теги: deepseek, llm, prompt-engineering, ai-slop, vibe-coding | высокий, бесплатно |
| Reddit r/LocalLLaMA | 500k+, англоязычные | пост с конкретикой, без рекламы | средний |
| Hacker News (Show HN) | инженеры | 3–4 предложения, честно про ограничения | низкий, но пик трафика |
| VC.ru / Habr | RU, читают статьи | разбор «почему ИИ делает одинаковые сайты» | высокий для RU |
| Telegram-каналы про ИИ и фронтенд | RU | 1 абзац + ссылка, по договорённости с админом | высокий |
| Product Hunt | англоязычные | страница продукта | низкий без подготовки |

Игровые площадки (uGame и подобные) не подходят: там нет людей с задачей «убрать нейрослоп из вёрстки», пост утонет и будет выглядеть как спам.

## Готовый текст: Reddit (EN)

> **I got tired of LLM sites looking identical, so I wrote rules instead of prompts**
>
> Every generated landing page has the same purple gradient, three feature cards with emoji icons, and `backdrop-filter` glass. My fix: before writing HTML the model must ask 4 questions (minimalism / design-accent / utilitarian / poster; density; theme; content), and before delivering it must run 10 separate checks — build, run, edge cases, I/O errors, security, accessibility, responsive at 320/768/1280, design-rule re-read, weight, full diff.
>
> The trick that helped most: ban square-bracket placeholders in visible UI. A model that writes `[product name]` is not designing, it is refusing to work.
>
> All prompts are in Russian, plain markdown, MIT: https://github.com/mgtoon/deepseek-skills — live copy page: https://mgtoon.github.io/deepseek-skills/
>
> What I have not solved: it still drifts on long single-file generations, and the 10-pass check costs tokens.

## Готовый текст: Show HN (EN)

> **Show HN: Anti-slop prompt rules for DeepSeek (brief + 10-pass self-review)**
>
> A set of markdown skills that force the model to ask four design questions before writing markup and to run ten separate review passes before shipping. Includes a banned-pattern list (purple gradients, glass panels, emoji icons, fake testimonials) and an explicit ban on `[placeholder]` text in the UI. MIT, Russian, copy-paste.

## Готовый текст: VC.ru / Habr (RU)

> **Почему сайты от ИИ выглядят одинаково и что с этим делать**
>
> Открываешь генерацию — и почти всегда получаешь одно и то же: градиент из фиолетового в синий, три карточки с иконками в кружках, «Trusted by 10 000+», радиусы 24 px у всего и текст «в современном мире».
>
> Причина не в модели, а в дефолте: если не задать рамку, она берёт самый частый вариант из обучающих данных.
>
> Я собрал набор правил, который эту рамку задаёт. Работает в два шага. Первый — бриф: четыре вопроса с вариантами (минимализм / дизайн-акцент / утилитарный / плакатный, плотность, тема, контент). Второй — приёмка: десять отдельных проходов по сборке, границам, доступности, адаптиву, безопасности и дизайну. Восьмой проход требует перечитать правила дизайна, а не вспоминать их.
>
> Отдельно — про квадратные скобки. Пока в правилах было «не выдумывай контент, пиши `[название продукта]`», модель честно собирала каркас из заглушек и называла это готовой страницей. Пришлось запретить плейсхолдеры в видимом интерфейсе: либо вопрос, либо рабочий текст.
>
> Репозиторий: https://github.com/mgtoon/deepseek-skills (MIT). Сайт с кнопкой «скопировать»: https://mgtoon.github.io/deepseek-skills/

## Готовый текст: Telegram (RU, короткий)

> Собрал правила для DeepSeek, чтобы он не делал одинаковые сайты: перед вёрсткой спрашивает про направление (минимализм или дизайн-акцент), после — прогоняет 10 проверок, включая перечитывание дизайн-правил. Заглушки вида `[название продукта]` запрещены. Скопировал → вставил первым сообщением.
> https://mgtoon.github.io/deepseek-skills/

## Чек-лист перед публикацией

1. Ссылка открывается в приватном окне, `index.html` и `link.html` живые.
2. В репозитории заполнены topics (12 штук) и описание.
3. В README первый экран отвечает «что я получу», без истории проекта.
4. Скриншот страницы приложен к посту — посты со скриншотом открывают в 2–3 раза чаще.
5. В каждом сообществе прочитаны правила: где-то self-promotion запрещён в понедельник, где-то только по пятницам.
6. Один пост — одно сообщество. Кросспостинг одинакового текста палится и банится.

## Чего не делать

- Писать в игровые и нерелевантные сообщества «поддержите репозиторий» — это спам.
- Покупать звёзды и накручивать форки: GitHub это видит, а люди — тем более.
- Отвечать ссылкой в чужих тредах без вопроса по теме.
- Обещать в посте то, чего в правилах нет: «полностью убирает ИИ-стиль» — неправда, «задаёт рамку и заставляет проверять» — правда.
