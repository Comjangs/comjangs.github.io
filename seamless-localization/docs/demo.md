# Demo

The demo shows Seamless Localization in ten languages: English, German, Spanish, French, Brazilian Portuguese, Russian, Japanese, Korean, Simplified Chinese, and Traditional Chinese. It uses only its own tables and fonts, so your tables and fonts are not changed.

## Import the demo
Choose **Tools > Seamless Localization > Import Demo** and click **Import**. In Unity 6.6 and later, the import window warns that the package has no signature and shows **Import Anyway**. Unity shows this for every package not signed by an organization you belong to, so click **Import Anyway**. The demo is placed in the **Samples** folder inside the Seamless Localization folder. The Localization package adds the demo languages your project lacks as locales inside that folder; on the settings page they appear only when the demo's font table (SL Demo Fonts) is selected, where you can also try your own fonts. The demo uses the Noto fonts included in Seamless Localization, and they are registered in Addressables when the import finishes so they load in Play.

## Try it
- Open the **Demo** scene in the Samples folder.
- Press Play and switch languages with the buttons at the bottom, or use the **Localization Preview** overlay in the Scene view.

## Remove the demo
When you finish with the demo, choose **Tools > Seamless Localization > Remove Demo** (or click **Remove Demo** on **Demo Info**). It lists what it will do and asks first. It closes the demo scene if it is open, removes the demo languages (the locales inside the demo folder), sets the font table in Project Settings back to Fonts if it points to the demo's font table, deletes the Samples folder, and removes the Localization Addressables groups left empty. Locales are project-wide, so the added ones would otherwise stay in your game: a player whose system language is one of them could start in a language your game has no translations for. Your own locales, tables, and fonts are not changed. **Import Demo** brings the demo back.

## What it shows
- **Left and right** — The same text with the official Localize String Event on the left and Localized TMP Text on the right. On the left the font does not change, so Japanese, Korean, and Chinese show missing glyphs. On the right the font follows the locale. TextMesh Pro logs a Console warning for each missing character in the left text; these warnings are expected.
- **Title and body** — The title uses the Font.Title role and the body uses Font.Body, each with its own font per locale.
- **Counter** — Click **Add item** to update a Smart String argument from code with `SetArguments`.
- **Dropdowns** — Below the panels, a TextMesh Pro dropdown on the left keeps its English options, because the Localization package has no component for dropdown options. The Localized TMP Dropdown on the right switches its options and font with the locale and keeps the selected option.

## Fonts
The demo uses Noto Sans, Noto Sans JP, Noto Sans KR, Noto Sans SC, and Noto Sans TC in Regular and Bold, under the SIL Open Font License. See **Third-Party Notices.txt** in the Seamless Localization folder. You can use these fonts in your own project under that license.
