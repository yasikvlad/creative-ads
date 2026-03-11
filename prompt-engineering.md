# Мастер-гайд по AI-промтам для рекламных креативов

5 инструментов генерации. Для каждого: структура промта, лучшие практики, параметры, примеры.

---

## 1. Midjourney

### Структура промта

```
[Субъект], [действие/поза], [окружение/фон], [стиль фотографии], [камера/объектив], [освещение], [цветовая палитра], [настроение] --ar [соотношение] --v 6.1 --style raw
```

### Параметры

| Параметр | Значение | Когда |
|----------|----------|-------|
| --v 6.1 | Версия модели | Всегда |
| --style raw | Меньше "приукрашивания" | Для реалистичных фото |
| --ar X:Y | Соотношение сторон | Всегда (см. platform-specs.md) |
| --s 50-150 | Стилизация | 50 = реалистично, 150 = художественно |
| --q 1 | Качество (по умолчанию) | Стандартное |
| --no [элемент] | Исключить элемент | Если нужно убрать что-то |
| --chaos 0-100 | Вариативность | 0 = предсказуемо, 20-40 для тестов |

### Стили для рекламы

| Стиль | Ключевые слова в промте | Когда |
|-------|------------------------|-------|
| Документальный | documentary photography, candid, natural, 35mm film | Pain-agitate, lifestyle |
| Студийный | studio lighting, clean background, product shot | Product-hero, offer |
| UGC | iPhone photo, casual, authentic, slightly imperfect | TikTok, social proof |
| Кинематографический | cinematic, anamorphic, shallow depth of field | Before/After, transformation |
| Минималистичный | minimal, clean, white space, modern design | Text-heavy, infographic |
| Эмоциональный | intimate, close-up, emotional, soft light | Pain, transformation |

### Камеры и объективы для реализма

| Тип | Ключевые слова | Эффект |
|-----|---------------|--------|
| Портрет | Canon R5, 85mm f/1.4 | Мягкое боке, фокус на лице |
| Lifestyle | Sony A7III, 35mm f/1.8 | Широкий контекст, естественно |
| Деталь | Canon 100mm macro | Крупный план, текстура |
| Общий план | 24mm wide angle | Пространство, контекст |
| UGC | iPhone 15, selfie | Аутентичность |

### Примеры по углам

**Pain-agitate (ступень 0-1):**
```
A 35-year-old woman sitting alone on bed at 3am, phone glow illuminating tired face, self-help books scattered on nightstand, documentary photography, Canon R5 35mm f/1.8, blue ambient light from phone screen, muted blue-grey tones, exhausted and anxious mood --ar 1:1 --v 6.1 --style raw
```

**Transformation (ступень 3-4):**
```
Split composition, left side: exhausted woman in dark room blue tones, right side: same woman radiating confidence in bright sunlit room warm tones, clean dividing line, before and after concept, cinematic photography, balanced lighting --ar 4:5 --v 6.1 --style raw
```

**Social proof (ступень 4-5):**
```
Smiling woman in her 30s holding phone showing positive results, cozy home office background, warm natural window light, authentic genuine expression, iPhone selfie style, casual outfit, slightly imperfect framing --ar 1:1 --v 6.1 --style raw
```

---

## 2. DALL-E (DALL-E 3)

### Структура промта

```
[Детальное описание сцены]. [Стиль и техника]. [Композиция и ракурс]. [Освещение и цвет]. [Настроение].
```

### Особенности DALL-E

- Промты на **английском** дают лучший результат
- Поддерживает **текст на изображении** (указывай в кавычках)
- Фиксированные размеры: 1024×1024, 1024×1792, 1792×1024
- Нет параметров вроде --ar, размер указывается при вызове API
- Более буквально интерпретирует промт (описывай точнее)

### Размеры

| Платформа | Размер DALL-E | Примечание |
|-----------|---------------|------------|
| Meta Feed, Google Square | 1024×1024 | 1:1 |
| Stories, Reels, TikTok | 1024×1792 | ~9:16 |
| YouTube, Google Landscape | 1792×1024 | ~16:9 |

### Пример промта

**Pain-agitate:**
```
Photorealistic image of a woman in her mid-30s sitting on the edge of her bed at 3 AM. Her face is illuminated by the blue glow of her smartphone. She looks exhausted with dark circles under her eyes. Self-help books are scattered on the nightstand. The room is dark with blue-grey ambient tones. Documentary photography style with natural, candid feel. The mood is isolated and anxious.
```

**Text-heavy (с текстом на изображении):**
```
Clean minimalist graphic design on warm cream background. Large bold text in the center reading "90% don't know this". Subtle geometric shapes in soft coral and terracotta colors. Modern sans-serif typography. Clean and professional look suitable for social media advertising.
```

---

## 3. Nano Banana Pro

### Структура промта

```
[Описание сцены], [стиль визуала], [композиция], [палитра], [формат/размер]
```

### Особенности

- Оптимизирован для **коммерческих визуалов**
- Хорошо работает с **product shots** и **branding**
- Поддерживает указание формата в промте
- Менее детализированный промт, чем Midjourney

### Стили для рекламы

| Стиль | Ключевые слова |
|-------|---------------|
| Product | clean product photography, studio, white background |
| Lifestyle | lifestyle shot, natural setting, authentic |
| Branding | brand visual, corporate, polished |
| Social Media | social media graphic, vibrant, eye-catching |
| Minimal | minimalist, clean lines, negative space |

### Пример промта

**Lifestyle (ступень 0-1):**
```
Woman sitting alone on bed late at night looking at phone, tired expression, messy hair, blue phone glow on face, dark bedroom with soft shadows, documentary lifestyle photography, muted blue-grey palette, square format 1:1
```

**Product-hero (ступень 4-5):**
```
Digital course mockup on modern laptop screen, woman smiling on screen, surrounded by floating benefit icons, clean white background with soft gradient, professional product photography, warm coral and white palette, vertical format 9:16
```

---

## 4. Higgsfield

### Структура промта

Заточен под **вертикальное видео** (Reels/TikTok), **UGC-стиль**.

```
[Действие персонажа], [UGC/selfie стиль], [вертикальный формат], [разговор на камеру или lifestyle], [длительность], [настроение]
```

### Особенности

- Специализация: **UGC-видео для соцсетей**
- Вертикальный формат по умолчанию
- Лучший результат с **talking head** и **lifestyle** сценами
- Не подходит для кинематографического стиля

### Типы контента

| Тип | Промт-паттерн | Когда |
|-----|--------------|-------|
| Talking head | "[Person] talking directly to camera, selfie angle..." | Story, myth-busting |
| Lifestyle | "[Person] doing [action] in [location]..." | Before/after, transformation |
| Reaction | "[Person] reacting to [something] with [emotion]..." | Hook, pain |
| Tutorial | "[Person] showing [process] step by step..." | Education, solution |

### Примеры

**Hook (ступень 0-1):**
```
Young woman talking directly to camera in her bedroom at night, selfie style, vertical format, she looks tired and frustrated, blue phone light on her face, authentic UGC feel, she starts speaking with urgency about not being able to sleep, warm indoor lighting, 3 seconds, anxious and relatable tone
```

**Story (ступень 1-2):**
```
Woman in her 30s sitting in cozy living room, talking to camera in confessional style, vertical format, she shares personal story about trying everything for anxiety, genuine emotional delivery, natural daylight from window, 15 seconds, vulnerable but hopeful tone
```

**Transformation (ступень 3-4):**
```
Split screen effect: left side shows stressed woman in dark room, right side shows same woman smiling confidently in bright setting, vertical format, dramatic transition between two states, before and after concept, 5 seconds, inspiring and empowering tone
```

---

## 5. Runway / Sora

### Структура промта (покадровый)

```
Scene [N]: [Описание сцены], [движение камеры], [стиль], [освещение], [длительность]
```

### Движения камеры

| Движение | Ключевые слова | Эффект |
|----------|---------------|--------|
| Статика | static shot, locked off | Стабильность, акцент на субъекте |
| Наезд | slow push in, camera push in | Внимание, интимность |
| Отъезд | slow pull back, camera pulls back | Контекст, reveal |
| Панорама | slow pan left/right | Обзор, переход |
| Tracking | tracking shot, following | Движение, энергия |
| Crane | crane up/down | Масштаб, драматизм |
| Handheld | handheld, slight shake | Документальность, UGC |
| Timelapse | time-lapse, accelerated | Трансформация, время |

### Стили

| Стиль | Когда | Ключевые слова |
|-------|-------|---------------|
| Documentary | Pain-agitate, real stories | documentary, handheld, natural light |
| Cinematic | Transformation, premium | cinematic, anamorphic, color graded |
| UGC | TikTok, authentic | selfie camera, smartphone footage |
| Commercial | Product, offer | polished, clean, professional |
| Dramatic | Myth-busting, reveal | dramatic lighting, high contrast |

### Пример полного сценария (30 сек, ступень 0-1)

```
Scene 1: Close-up of a woman's face illuminated by phone screen in dark bedroom, slight camera push in, documentary style, blue ambient light, 3 seconds

Scene 2: Same woman sitting up in bed rubbing her eyes, slow pan from hands to face revealing exhaustion, warm practical lighting from bedside lamp, 4 seconds

Scene 3: Montage of failed attempts: pill bottles, meditation app on phone, herbal tea cooling untouched, quick cuts between static shots, muted desaturated tones, 5 seconds

Scene 4: Woman looking at phone screen showing a hopeful message, her expression softens, gentle camera push in on her face, warm golden light gradually replacing blue, 5 seconds

Scene 5: Time-lapse of sunrise through bedroom window, woman doing calm breathing exercise by the window, camera slowly pulls back to reveal peaceful room, golden hour light flooding in, 8 seconds

Scene 6: Woman smiling with genuine confidence in bright sunlit room, static shot with gentle bokeh background, warm natural light, text overlay appears, 5 seconds
```

### Пример для TikTok (15 сек, Higgsfield-стиль в Runway)

```
Scene 1: Young woman picks up phone and starts talking to camera, bedroom setting, selfie angle vertical format, natural indoor lighting, authentic and casual, 3 seconds

Scene 2: Same woman getting animated about the topic, hand gestures, slight zoom in, continues talking with conviction, 5 seconds

Scene 3: Quick cut to lifestyle shot of woman sleeping peacefully, soft morning light, gentle camera movement, 4 seconds

Scene 4: Back to talking head, woman smiles and points down (to link), text overlay with CTA, 3 seconds
```

---

## Универсальные правила промт-инжиниринга

### 1. Конкретность

| Плохо | Хорошо |
|-------|--------|
| A sad woman | A 35-year-old woman with dark circles under her eyes, sitting alone on the edge of her bed at 3am |
| Nice lighting | Warm golden hour light streaming through a window, soft shadows |
| Beautiful background | Cozy bedroom with white linen, potted plants, morning light |

### 2. Язык промта — всегда английский
Даже если целевая аудитория русскоязычная, промты для AI пишутся на английском. Текст на русском добавляется поверх в дизайне.

### 3. Порядок элементов (от важного к деталям)
1. Субъект (кто/что)
2. Действие (что делает)
3. Окружение (где)
4. Стиль (как выглядит)
5. Технические детали (камера, свет)
6. Параметры (--ar, --v)

### 4. Консистентность серии
Для A/B вариаций используй **общую базу промта** и меняй только тестируемый элемент:

```
БАЗА: A 35-year-old woman, documentary photography, Canon R5, muted tones --v 6.1 --style raw

Вариация A: [БАЗА] + sitting alone on bed at 3am, phone glow --ar 1:1
Вариация B: [БАЗА] + close-up of hands clutching phone anxiously --ar 1:1
Вариация C: [БАЗА] + standing by window looking out at dark city --ar 1:1
```

### 5. Текст на изображении
- **Midjourney:** Плохо генерирует текст. Не включай текст в промт — добавляй в дизайне.
- **DALL-E:** Умеет генерировать текст. Указывай в кавычках: `text reading "Your headline here"`
- **Nano Banana Pro:** Средне. Лучше добавлять текст отдельно.

### 6. Таблица соответствия: угол → инструмент

| Угол | Лучший инструмент | Почему |
|------|-------------------|--------|
| Pain-agitate (статика) | Midjourney | Реализм, эмоция, детализация |
| Text-heavy | DALL-E | Генерация текста на изображении |
| Before/After | Midjourney | Контроль над композицией |
| Social proof / UGC (статика) | Nano Banana Pro | Быстрый, коммерческий стиль |
| Product-hero | Nano Banana Pro | Заточен под продуктовые визуалы |
| UGC видео | Higgsfield | Специализация на вертикальном UGC |
| Кинематографическое видео | Runway/Sora | Качество, контроль камеры |
| TikTok нативное | Higgsfield | UGC-стиль, вертикальный формат |
| YouTube pre-roll | Runway/Sora | Горизонтальный, кинематографичный |
