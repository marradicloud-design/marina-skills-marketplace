# Midjourney prompt template

Midjourney работает с текстовыми промтами, не JSON. Структура промта строгая, порядок параметров важен.

## Базовая структура

```
[medium] [subject], [environment], [composition], [lighting], [color palette], [mood], [style references], [technical], [parameters]
```

## Шаблон промта

```
[medium: cinematic photograph / editorial fashion shot / commercial product photography / hyper-realistic portrait]

[subject: подробно — типаж, поза, выражение, одежда, ключевые черты. Для продукта: материал, цвет, форма, состояние]

[environment: где находится — студия / интерьер / улица / абстрактный фон. Текстуры, поверхности, окружающие объекты]

[composition: rule of thirds / centered / golden ratio / extreme close-up / wide shot / overhead. Что в фокусе, что на периферии]

[lighting: golden hour / soft daylight / studio softbox / dramatic side light / neon. Направление, температура, контраст]

[color palette: 3–5 цветов с настроением — warm earthy tones / cool minimalist / saturated bold / muted pastel]

[mood: emotional tone — serene, energetic, luxurious, intimate, dramatic, playful]

[style references: in the style of [photographer/movement] / editorial Vogue / Wes Anderson aesthetic / Helmut Newton noir]

[technical: 35mm / 85mm lens / shallow depth of field / film grain / 8k detail / shot on Hasselblad]

--ar [9:16 / 1:1 / 16:9 / 4:5] --style raw --v 7 --stylize [50–500] --chaos [0–30]
```

## Параметры под задачи

| Задача | Aspect ratio | Параметры |
|---|---|---|
| WB карточка (главное фото) | `--ar 3:4` | `--style raw --stylize 100` |
| Reels / TikTok / Shorts стартовый кадр | `--ar 9:16` | `--style raw --stylize 150` |
| Инфографика / баннер | `--ar 1:1` | `--style raw --stylize 50` |
| Imagine-кадр для image-to-video в Kling | `--ar 9:16` | `--style raw --stylize 100 --v 7` |
| Артовый key visual | `--ar 16:9` | `--stylize 300 --chaos 15` |
| Lifestyle с человеком | `--ar 4:5` | `--style raw --stylize 150` |

## Референсы по изображению

- `--cref [URL]` — character reference (сохранить лицо/типаж)
- `--cw [0–100]` — character weight (100 = жёстко держим лицо)
- `--sref [URL]` — style reference (взять стиль с картинки)
- `--sw [0–1000]` — style weight
- `--no [объект]` — negative, что не должно быть в кадре

## Пример готового промта (продукт-lifestyle для WB)

```
cinematic commercial photograph of a ceramic matte-white aroma diffuser on a warm oak wooden table, soft morning sunlight from a left window casting long shadows, blurred linen curtains in background, eucalyptus branch and ceramic mug nearby, shallow depth of field with diffuser sharply in focus, warm earthy palette of cream beige terracotta soft green, serene minimalist Scandinavian mood, in the style of editorial home interior photography, shot on Hasselblad with 85mm lens, soft focus background, film grain, 8k detail --ar 3:4 --style raw --stylize 100 --v 7 --no text logo cluttered modern
```

## Запреты для Midjourney-промтов

- НЕ использовать русский язык в промте — Midjourney хуже понимает кириллицу
- НЕ ставить запятые внутри одного концепта
- НЕ перегружать стилевыми референсами (макс 2)
- НЕ забывать `--no` для типичных артефактов (text, watermark, deformed, extra limbs)
- НЕ ставить `--stylize > 500` для коммерческих задач — теряется фотореалистичность
