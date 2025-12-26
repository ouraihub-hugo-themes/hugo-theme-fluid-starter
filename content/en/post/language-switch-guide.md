---
title: "Multi-language Configuration and Language Switching Guide"
date: 2024-12-25
categories:
  - Tutorial
tags:
  - Hugo
  - Multi-language
  - Configuration
  - i18n
description: "A detailed guide on how to configure multi-language support and use the language switching feature in Hugo Theme Fluid"
index_img: "https://images.unsplash.com/photo-1451187580459-43490279c0fa?w=800&h=400&fit=crop"
---

Hugo Theme Fluid provides complete multi-language support, allowing you to easily create a multilingual blog. This article provides a detailed guide on how to configure and use the language switching feature.

<!--more-->

## Features

- 🌐 Support for multiple languages (Simplified Chinese, Traditional Chinese, English, Japanese, etc.)
- 🔄 Navigation bar language switching dropdown menu
- 📄 Automatic detection of translated pages
- 🏠 Redirect to target language homepage when no translation exists
- 🎨 Beautiful dropdown menu styling

## Configuration Steps

### 1. Configure hugo.toml

Configure multi-language settings in `config/_default/hugo.toml`:

```toml
# Default language
defaultContentLanguage = "zh-CN"
defaultContentLanguageInSubdir = false

# Multi-language configuration
[languages]
[languages.zh-CN]
languageCode = "zh-CN"
languageName = "简体中文"
weight = 1
title = "My Blog"

[languages.en]
languageCode = "en"
languageName = "English"
weight = 2
title = "My Blog"

[languages.zh-TW]
languageCode = "zh-TW"
languageName = "繁體中文"
weight = 3
title = "My Blog"

[languages.ja]
languageCode = "ja"
languageName = "日本語"
weight = 4
title = "My Blog"
```

**Configuration Description:**

| Parameter | Description |
|-----------|-------------|
| `defaultContentLanguage` | Default language code |
| `defaultContentLanguageInSubdir` | Whether default language uses subdirectory (e.g., `/zh-CN/`) |
| `languageCode` | Language code for HTML lang attribute |
| `languageName` | Language display name |
| `weight` | Sort weight, smaller numbers appear first |
| `title` | Site title for that language |

### 2. Configure Language-specific Menus (Optional)

If you need different menus for different languages, use language suffixes in `menus.toml`:

```toml
# Simplified Chinese menu
[[menus.zh-CN.main]]
name = "Home"
url = "/"
weight = 1

[[menus.zh-CN.main]]
name = "Archives"
url = "/archives/"
weight = 2

# English menu
[[menus.en.main]]
name = "Home"
url = "/"
weight = 1

[[menus.en.main]]
name = "Archives"
url = "/archives/"
weight = 2
```

### 3. Create Multi-language Content

Hugo supports two ways to organize multi-language content:

#### Method 1: Filename Suffix (Recommended)

```
content/
├── post/
│   ├── hello-world.md        # Default language
│   ├── hello-world.en.md     # English version
│   └── hello-world.zh-TW.md  # Traditional Chinese version
```

#### Method 2: Language Directories

```
content/
├── zh-CN/
│   └── post/
│       └── hello-world.md
├── en/
│   └── post/
│       └── hello-world.md
└── zh-TW/
    └── post/
        └── hello-world.md
```

### 4. Translate Interface Text

Theme interface text translation files are located in the `i18n/` directory:

```
i18n/
├── zh-CN.toml    # Simplified Chinese
├── en.toml       # English
├── zh-TW.toml    # Traditional Chinese
├── ja.toml       # Japanese
├── de.toml       # German
├── es.toml       # Spanish
├── ru.toml       # Russian
└── eo.toml       # Esperanto
```

## Language Switching Component

### Display Location

The language switch button is located on the right side of the navigation bar, between the search button and theme toggle button.

### Interaction

1. **Hover/Click** - Display language dropdown menu
2. **Select Language** - Click target language to switch

### Switching Logic

- **Has Translation** - Navigate to the translated version of the current page
- **No Translation** - Navigate to the target language homepage

## Supported Language Identifiers

| Language Code | Display | Language Name |
|---------------|---------|---------------|
| `zh-CN` | 简 | Simplified Chinese |
| `zh-TW` | 繁 | Traditional Chinese |
| `zh-HK` | 港 | Hong Kong Traditional |
| `en` | EN | English |
| `ja` | 日 | Japanese |
| `de` | DE | German |
| `es` | ES | Spanish |
| `ru` | RU | Russian |
| `eo` | EO | Esperanto |

## FAQ

### Q: How to disable language switching?

Just configure only one language, and the language switching component will automatically hide.

### Q: How to add a new language?

1. Add language configuration in `hugo.toml`
2. Create corresponding `i18n/xx.toml` translation file
3. Create content files for that language

### Q: How are translated pages linked?

Hugo automatically links translated pages by filename:
- `hello-world.md` and `hello-world.en.md` are automatically linked
- Use the `.Translations` variable to get all translated versions

### Q: How to set default language without subdirectory?

```toml
defaultContentLanguage = "zh-CN"
defaultContentLanguageInSubdir = false
```

This way the default language URL is `/post/hello/` instead of `/zh-CN/post/hello/`.

## Best Practices

1. **Choose appropriate default language** - Based on your main audience
2. **Keep translations synchronized** - Regularly update all language versions
3. **Use filename suffixes** - Easier to manage and maintain
4. **Complete i18n translations** - Ensure all interface text is translated
5. **Test language switching** - Ensure switching between languages works correctly

## Summary

Hugo Theme Fluid's multi-language support allows you to easily create a blog for global readers. With simple configuration, you can achieve:

- Multi-language content management
- Automatic language switching
- Interface text localization
- Beautiful language selector

Hope this tutorial helps you successfully configure your multilingual blog!
