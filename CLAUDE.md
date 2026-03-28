# Brainbreak Project Notes

## Adding New Tags

Whenever a new tag is added to a brainbreak's frontmatter, a corresponding emoji entry must also be added to `static/style.css`.

### Pattern
- Single-word tags: `#tag_movement:before { content: "🏃‍♂️"; }`
- Multi-word tags: `[id="tag_older students"]::before { content: "🔝"; }`

Tag IDs are the tag name lowercased with spaces kept as-is. Add new entries near the existing tag block (around line 188).

### Existing tags and emojis
| Tag | Emoji |
|-----|-------|
| Thought Experiment | 💭 |
| Team Work | 👥 |
| Word Play | 📝 |
| Movement | 🏃‍♂️ |
| Chatting | 💬 |
| Observation | 👀 |
| Energising | 💪 |
| Fun | 🤓 |
| Maths | 📓 |
| Calming | 🤫 |
| Silent | 💤 |
| Drawing | 🖊️ |
| Touch | 👏 |
| Trivia | 🤔 |
| Outside | 🏞️ |
| Rhythmic | 🥁 |
| Trolleyology | 🚃 |
| Older Students | 🔝 |
| Younger Students | 🧒 |
| Call to Attention | 🔔 |

## Brainbreak File Format

Files live in `content/` as markdown with Hugo frontmatter:

```
---
title: "Title"
date: YYYY-MM-DD
tags: ["Tag1", "Tag2"]
author: learningnow
---
```

- Write in direct, read-aloud instructions using collective first person ("we")
- Plain, concrete language -- teacher should be able to read it word for word
