# Text Converter

Already localized your project with the official **Localize String Event**? The Text Converter switches those texts to **Localized TMP Text** in a few clicks, so their fonts follow the locale and CJK text no longer shows missing glyphs. Your tables and keys stay the same, and each conversion can be reverted.

## Quick start
- **Commit your project to version control.** Prefab changes cannot be undone with Undo.
- Open **Edit > Project Settings > Seamless Localization**. If your open scenes use Localize String Event, the status list says how many. Click **Convert** there, or open **Tools > Seamless Localization > Text Converter**.
- The converter scans your open scenes and every prefab, then lists the texts under **Ready to convert**. Clear the check box of any text you want to keep.
- Click **Convert**. The done screen shows how many texts were converted and lets you undo the scene changes.

To convert one text, open the menu (⋮) of its Localize String Event component and choose **Convert to Localized TMP Text**.

## What changes
| Before | After |
|---|---|
| TextMesh Pro text + Localize String Event | TextMesh Pro text + Localized TMP Text |
| String reference and Smart String local variables on the event | The same string reference and local variables on Localized TMP Text |
| Font set on the TextMesh Pro text | Font from the font table for the Default Font Role (change it under Options) |

Texts inside prefab instances are converted through their prefab assets, so every scene that uses the prefab gets the change. Scenes that are not open are not scanned; open them and scan again. Scenes and prefabs inside the Seamless Localization folder, such as the demo's comparison text, are never converted.

## Needs your attention
Texts that cannot be converted safely are listed with the reason and what to do. Use **Select** to find the object.

| Reason | What to do |
|---|---|
| The Localize String Event has no listener | Nothing sets this text. Remove the Localize String Event if it is not needed, or add Localized TMP Text by hand. |
| The Localize String Event has other listeners | Move the other listeners elsewhere, then convert it from the Localize String Event menu (⋮). |
| The Localize String Event sets something other than this text | The event updates another object or property. Leave it as it is, or convert it by hand. |

## Options
- **Include Plain Texts** — Also adds Localized TMP Text in Font Only mode to TextMesh Pro texts without a Localize String Event, such as player names or numbers set by your code. Their font then follows the locale.
- **Font Role** — The font role given to converted texts. The Default Font Role is used unless you change it.

## Reverting
- **Right after converting** — Click **Undo scene changes** on the done screen, or use Undo. This reverts the texts in open scenes.
- **Later, or in a prefab** — Open the menu (⋮) of a Localized TMP Text component and choose **Revert to Localize String Event**. A Localize String Event with the same string reference and a listener that sets the text is created again, and Localized TMP Text is removed. The text goes back to the font saved in the TextMesh Pro component. A text in Font Only mode only has Localized TMP Text removed.
