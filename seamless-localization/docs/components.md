# Components

## Localized TMP Text
Shows a localized string on a TextMesh Pro text and switches its font with the locale. The string and the font load separately, and they are applied together once both are ready for the locale, so text never flickers with missing glyphs.

Add it in one of these ways:
- **New text** — Right-click in the Hierarchy and choose **UI > Text - Localized TMP**.
- **New button or input field** — Choose **UI > Button - Localized TMP** or **UI > Input Field - Localized TMP**. The button label and the input field placeholder get Localized Text. The typed text of the input field gets Font Only, because the input field sets it.
- **New dropdown** — Choose **UI > Dropdown - Localized TMP**. It gets **Localized TMP Dropdown** (below), which sets the options and the font of the caption and items.
- **Existing text** — Open the menu (⋮) of the TextMesh Pro component and choose **Localize with Seamless Localization**.
- **Add Component > Seamless Localization > Localized TMP Text**.
- **Texts that already use Localize String Event** — Use the [Text Converter](text-converter.md).

The Default Font Role is assigned automatically.

- **Mode** — Localized Text sets the string and font; Font Only changes only the font. Use Font Only for text that your code sets, such as player names.
- **String** — The localized string to show.
- **Font Table** — The Asset Table Collection this text takes its font from. New components get the Font Table from [Project Settings](settings.md#fonts). An info icon appears when a text uses another table, such as the demo's SL Demo Fonts.
- **Font Role** — The font role whose font is applied for the current locale: a key in the Font Table. New components get the Default Font Role from [Project Settings](settings.md#fonts). Changing the font role keeps the Font Table.
- **Preview Arguments** — Smart String arguments used only for the editor preview. When empty, every argument uses the Placeholder Argument from [Project Settings](settings.md#preview). Values that read as numbers, such as `3`, are passed as numbers, so plural forms work in the preview. When the arguments do not fit the Smart String, the preview keeps the previous text and logs one warning for that text.

In Edit Mode the component previews the string and font for the selected locale. Preview values are not saved to the scene.

### Localization Preview overlay
The **Localization Preview** overlay in the Scene view switches the preview locale for every Localized TMP Text at once. Pick a locale from the list, or use ◀ and ▶ to step through the locales and check each language. It works in Edit Mode and Play Mode, and it changes the same locale as the Localization Scene Controls window.

Like other overlays, you can move it, dock it to the Scene view toolbar, or collapse it to an icon: right-click its title bar and choose **Collapse**. To show or hide it, open the Overlays menu of the Scene view (press the ` key in the Scene view).

If the font table has no font for the current locale, the text uses its current font and a warning is logged in the Editor.

### Scripting
| Member | Description |
|---|---|
| `SetKey(string key)` | Shows the entry with this key from the same table. |
| `SetEntry(TableEntryReference entry)` | Shows this entry (key or ID) from the same table. |
| `SetArguments(params object[] args)` | Sets Smart String arguments and refreshes the text. Call it before enabling the object to avoid formatting errors. |
| `Text` | The `LocalizedString` used by the component. |
| `Font` | The `LocalizedTmpFont` used by the component. |
| `Mode` | The current mode. |

## Localized TMP Dropdown
Shows localized options on a TextMesh Pro dropdown and switches the font of its caption and items with the locale. The options and the font are applied together once all of them are ready for the locale, so options never flicker with missing glyphs. The selected option stays selected.

Add it with **UI > Dropdown - Localized TMP**, or with **Add Component > Seamless Localization > Localized TMP Dropdown** on an existing TextMesh Pro dropdown. The Default Font Role is assigned automatically.

- **Options** — Each option's localized string and an optional image. In Play Mode these options replace the options of the TMP Dropdown. When the list is empty, the dropdown keeps its own options and only the font changes.
- **Font Table** and **Font Role** — The same as on Localized TMP Text above. The font is applied to the caption and to the item template.

If the list is open when the locale changes, it closes; it shows the new options when opened again. There is no Edit Mode preview, because changing the options would modify the scene.

### Scripting
| Member | Description |
|---|---|
| `SetOptions(params LocalizedString[] texts)` | Replaces the options. |
| `SetOptions(TableReference table, params string[] keys)` | Replaces the options with these keys from one table. |
| `Options` | The current options. |
| `Font` | The `LocalizedTmpFont` used by the component. |

Use the `value` of the TMP Dropdown to get or set the selected option.
