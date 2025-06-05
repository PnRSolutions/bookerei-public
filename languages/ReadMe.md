# Language Resource Manual

This document explains how to add a new language to Bookerei using `.resx` resource files.

---

## 1. Overview

Bookerei uses `.resx` files for localization. Each language has its own file, e.g.:

- `Translation.en.resx` (English)
- `Translation.de.resx` (German)
- `Translation.fr.resx` (French)
- etc.

All language files are stored in the `languages` directory.

---

## 2. Creating a New Language

### Step 1: Copy the Reference File

1. Use `Translation.en.resx` as your template.
2. Copy it and rename the copy to match your target language, e.g.:
   - For Spanish: `Translation.es.resx`
   - For Italian: `Translation.it.resx`

### Step 2: Translate the Values

- Open your new `.resx` file.
- For each `<data>` entry, translate the text inside the `<value>` tag.
- **Do not change the `name` attribute**—only translate the `<value>` content.

**Example:**

```xml
<data name="Add to the clipboard" xml:space="preserve">
  <value>Añadir al portapapeles</value>
</data>
```

### Step 3: Save and Test

- Save your new `.resx` file.
- Add it to version control (e.g., Git).

---

## 3. Submitting Your Language

### Option 1: Create a Pull Request (Recommended)

1. **Fork** the repository on GitHub.
2. **Create a new branch** for your language.
3. **Add your `.resx` file** to the `languages` folder.
4. **Commit** your changes with a descriptive message.
5. **Push** your branch to your fork.
6. **Open a Pull Request** to the main repository.

### Option 2: Send the File (Easier)

- If you cannot use GitHub, send your `.resx` file to the project maintainer by email or other means.

---

## 4. Language Codes

Use standard [ISO 639-1 language codes](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) for filenames:
- English: `en`
- German: `de`
- Spanish: `es`
- French: `fr`
- etc.

---

## 5. Tips

- Keep the structure and order of entries the same as the reference file.
- Comments in the file (inside `<comment>`) help clarify usage/context—do not translate comments unless needed.

---

## 6. Example Workflow

1. Copy `Translation.en.resx` → `Translation.es.resx`
2. Translate all `<value>` tags in `Translation.es.resx`
3. Add and commit the file
4. Open a pull request

---

## 7. Troubleshooting

- **Missing translations:** The app may fall back to English if a translation is missing.
- **Encoding:** Ensure the file is saved as UTF-8.
- **File location:** Place all language files in the `languages` directory.

---

## 8. Questions or Help

If you need help, open an issue on GitHub or contact the maintainers.

---
