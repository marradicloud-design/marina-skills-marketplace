# marina-skills marketplace

Личный marketplace Claude Code-плагинов для локального CC и Cowork-сессий.

## Плагины

### video-prompt-architect

Архитектор промтов для AI-видео и AI-image, заточенный под коммерческий результат.

**Стек моделей:**
- **Video** (по приоритету): Seedance 2, Runway, Kling
- **Image** (по приоритету): Nano Banana + GPT Image 2, затем Midjourney
- **Аналитики**: Claude, GPT, Gemini
- **Опциональные**: Veo 3, Nana (Banana Video)

**Что внутри:**
- 4 ролевых модуля (сценарист → режиссёр → оператор → креативный директор)
- 8 JSON/MD-шаблонов под конкретные модели
- 13-пунктовый чек-лист качества промта
- Стандартный + audit-workflow
- Шаблон сценария 15-сек ролика

## Установка

### Шаг 1 — добавить marketplace в settings.json

В `~/.claude/settings.json` (или в Cowork-сессии):

```json
{
  "extraKnownMarketplaces": {
    "marina-skills": {
      "source": {
        "source": "github",
        "repo": "marradicloud-design/marina-skills-marketplace"
      }
    }
  }
}
```

### Шаг 2 — установить плагин

В Claude Code:

```
/plugin install video-prompt-architect@marina-skills
```

### Шаг 3 — перезапустить Claude Code

Скилл активируется автоматически по триггерам: «промт под Seedance», «промт для Kling», «раскадровка», «сценарий ролика», «промо-ролик», «key visual», «AI-видео», «image-промт» и др.

## Обновления

После любых правок SKILL.md → push в эту репу → в Claude Code:

```
/plugin update video-prompt-architect@marina-skills
```

## Лицензия

MIT — личное использование, форки и адаптация под свой стек разрешены.
