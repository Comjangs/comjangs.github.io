# Quick Start

From import to a localized text in a few minutes. Each step links to the page with details.

## 1. Import
Import Seamless Localization. If Localization 1.5.13 or later or Unity UI 2.0.0 or later is missing, a dialog asks to install it when the import finishes; click **Install**. You can also run **Tools > Seamless Localization > Install Required Packages**. See [Requirements](index.md#requirements).

## 2. Set Up
Open **Tools > Seamless Localization > Settings**.

- Under **Status**, check the languages for your project. English and your system language are selected by default.
- Click **Set Up**. Localization Settings, the locales, and the font table are created in `Assets/Localization`. Existing assets are used instead of creating new ones.

See [Set Up](settings.md#set-up).

## 3. Fonts
Click **Fill Default Fonts** on the **Empty font slots** line. Each empty slot gets a Noto font for its locale, and the fonts are copied to `Assets/Localization/Fonts`. If TMP Essential Resources are missing, they are imported first and filling continues. To use your own fonts, drop TextMesh Pro font assets into the font table grid under **Fonts** instead.

See [Empty font slots](settings.md#empty-font-slots).

## 4. Strings
Open **Window > Asset Management > Localization Tables**, create a String Table Collection, and add keys with a translation for each locale. This is the official Localization workflow; see [the Localization Quick Start Guide](https://docs.unity3d.com/Packages/com.unity.localization@1.5/manual/QuickStartGuideWithVariants.html). When you add a language later with **Add Languages**, your string tables get an empty column for it.

## 5. Texts
- **New text** — Right-click in the Hierarchy and choose **UI > Text - Localized TMP**, then pick the **String**.
- **Existing TextMesh Pro text** — Open the menu (⋮) of the component and choose **Localize with Seamless Localization**.
- **Texts that already use Localize String Event** — Run **Tools > Seamless Localization > Text Converter**.

Each text gets the Default Font Role. Choose **Font Role** in the inspector to use another one, such as `Font.Title`. See [Localized TMP Text](components.md#localized-tmp-text).

## 6. Preview
Use the **Localization Preview** overlay in the Scene view to switch the locale in Edit Mode. Text and font change together. Press Play to check the same in Play Mode. See [Localization Preview overlay](components.md#localization-preview-overlay).

## Next
- [Demo](demo.md) — a ten-language scene that shows every feature.
- [Project Settings](settings.md) — font roles, the default font role, and the preview placeholder.
