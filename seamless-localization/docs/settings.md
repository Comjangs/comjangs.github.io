# Project Settings

Open **Tools > Seamless Localization > Settings**, or **Edit > Project Settings > Seamless Localization**. All settings live on this page and are saved to `ProjectSettings/SeamlessLocalizationSettings.asset`, so they are shared through version control.

## Reset to Defaults
Click the menu (⋮) at the top right of the page and choose **Reset to Defaults** to return every Seamless Localization setting to its default. Your Localization assets, tables, and fonts are not changed.

The settings file stays in `ProjectSettings` when Seamless Localization is removed. If you install it again later, a dialog shows the previous settings and asks whether to keep them or reset them. Updating to a new version does not ask.

## Status
Checks that your project is ready. Each failed check shows a help button and, when possible, a button that fixes it.

### Set Up
Shown when Localization Settings, locales or the font table are missing. Click **Set Up** to prepare everything in one step. A dialog lists what will happen before anything changes.

- Only missing items are handled. Existing assets are used instead of creating new ones: an existing Localization Settings asset is made active, and existing locales are added.
- New assets are created in `Assets/Localization`.
- When the project has no locales, choose languages with the checkboxes above the button: English, German, Spanish, French, Portuguese (Brazil), Russian, Japanese, Korean, Chinese (Simplified), Chinese (Traditional), and your system language if it is not in the list. English and your system language are selected by default. Add more later with [Add Languages](#add-languages).

To choose folders and locales yourself, use the buttons on each check below instead.

### Add Languages
After setup, the locales line has an **Add Languages** button. It shows the same language checkboxes; languages already in the project are checked and locked. Check more languages and click **Add**.

- The new locales are created in the folder of your existing locales, and their tables are added to the font table and, empty, to your string tables so you can start translating. Existing translations are not changed.
- A dialog then offers to run **Fill Default Fonts** for the new empty slots.
- For languages not in the list, use **Locale Generator** in **Project Settings > Localization**.
- A locale asset kept after **Remove Languages** is reused when you add the same language again.

### Remove Languages
With two or more locales, the locales line also has a **Remove Languages** button. Check the languages to remove and click **Remove**. At least one language must remain.

- The locales are removed from the project's language list, and their tables are removed from the font table.
- Translations (string tables) and the locale assets are kept, so adding a language again restores it.
- Locales added with the demo are not listed; **Remove Demo** removes them.

### Localization Settings missing
The Localization package has no active settings asset. Click **Open Localization** and create one on the Localization settings page.

### No locales
No locales are defined. Click **Open Localization** and add locales with **Add Locale** or **Add All**.

### TMP Essential Resources missing
The TextMesh Pro settings and shaders have not been imported into the project. Click **Import**. Fill Default Fonts also imports them first when they are missing, then continues.

### Font table missing
The font table set in **Fonts** does not exist. Click **Create** and choose a folder inside `Assets`. The table is created with one table per locale.

### Empty font slots
Some font slots have no font. Fill them in the font table grid under **Fonts**, or click **Fill Default Fonts**.

**Fill Default Fonts** fills only the empty slots with the Noto fonts included in Seamless Localization. Slots that already have a font are skipped, and so are locales that have no table in the font table yet; add their tables with **Add Table** first. A dialog lists the font for each slot before anything changes.

- Only the fonts your locales need are copied to `Assets/Localization/Fonts`, with Dynamic TextMesh Pro font assets and the font licenses. Fonts already copied there are reused.
- Japanese, Korean, Simplified Chinese and Traditional Chinese use Noto Sans JP, KR, SC and TC. Languages written in Latin, Greek or Cyrillic letters use Noto Sans. Other locales, such as Arabic or Thai, are skipped; assign their fonts yourself.
- Font roles whose names contain Title, Bold or Head get the Bold font. Other font roles get Regular.

### Fonts not in Addressables
Some fonts in the font table are not registered in Addressables, so they cannot load in Play and texts using them do not change. This happens when the font table comes from a package or a merge: the Localization package registers the table but not the fonts it uses. Click **Register** to register them.

## Fonts
Defines which TextMesh Pro font asset each locale uses for each font role.

- **Font Table** — The Asset Table Collection that holds fonts. Type a name, or click **Select** to pick an existing one. New texts use this table; a text can use another table with **Font Table** in its inspector.
- **Keep Dynamic Fonts Clean** — Glyphs that Dynamic fonts in font tables add while texts are shown (in the Editor or in Play Mode) are not saved to disk, so the font files do not change in version control. They are created again from the source font when needed. Changes you make to a font yourself, such as its fallback list, are still saved. On by default.
- **Font Roles** — The font roles used in your project, e.g. `Font.Body` and `Font.Title`. Each font role is a key in the font table. Removing a font role from this list does not delete its fonts from the table.
- **Default Font Role** — The font role assigned to newly added text components.

### Font table grid
Rows are the locales that have a table in the selected font table, plus your locales that do not have one yet (with **Add Table**). Locales added with the demo, inside the Seamless Localization folder, appear only in the demo's font table, marked **(demo)**; the locales line in Status counts them separately.

- Drop a font asset into a slot to assign it. Clear the slot to remove it. Changes support Undo.
- **Fill Empty** — Drop a font into this row to assign it to every empty slot in that column.
- **Add Table** — Adds the missing table for this locale. Shown when the locale was added after the font table was created.

## Preview
Controls the editor preview of [Localized TMP Text](components.md#localized-tmp-text).

- **Placeholder Argument** — The value used for every Smart String argument in the editor preview when a component has no Preview Arguments. Formatters that need a number, such as plural, read it as 0, so the preview shows, for example, `- items` instead of an error.
