# 2. Title

This document defines the conventions for **Title** metadata field. The goal is to ensure that song titles are displayed consistently across all players while clearly indicating specific versions, mixes, or edits.

## 2.1 General Structure

The Title tag must follow this structure: `{Base Title} {Version Suffix}`

- **Base:** The clear, official title of the song as published by the artist.
- **Version Suffix:** Optional. If present, it must be enclosed in parenthesees `()` and placed immediately after the base title, separated by a single space.
- **Character Set:** All UTF-8 characters are allowed.
- **Capitalization:** Must match the official capitalization of the base title. Version keywords inside the parentheses follow **Title Case** (e.g., `Extended Mix`, not `extended mix`), unless the artist specifically stylizes them otherwise.

---

## 2.2 Allowed Version Keywords

The following keywords are standardized for use within the parentheses. Do not invent new keywords; if a version does not fit, use the closest matching standard term.

| **Keyword** | **Usage** | **Example** |
| :---------- | :-------- | :---------- |
| `Extended Mix` | Club or extended versions with longer intros/outros. | `Song (Extended Mix)` |
| `Remix` | A remix by another artist. Requires the remixer's name. | `Song (Artist Remix)` |
| `Acoustic` | Stripped-down, unplugged versions. | `Song (Acoustic)` |
| `Instrumental` | Versions without vocals. | `Song (Instrumental)` |
| `Orchestral` | Versions performed by an orchestra. | `Song (Orchestral)` |
| `Live` | Live recording. Optionally includes location/year. | `Song (Live)` or `Song (Live at Wembley 1985)` |
| `Slowed` | Slowed down tempo (often with reverb). | `Song (Slowed)` |
| `Sped Up` | Increased tempo (nightcore style). | `Song (Sped Up)` |
| `Intro` | Tracks serving as an introduction. | `Song (Intro)` |
| `Interlude` | Short connection tracks. | `Song (Interlude)` |
| `Radio Edit` | Shortened version for radio play. | `Song (Radio Edit)` |
| `VIP` | "Variation In Production" (common in Drum & Bass/Dubstep). | `Song (VIP)` |

---

## 2.3 Complex Version Combinations

Tracks may have multiple attributes (e.g., a remix that is also extended and slowed). In such cases, combine the keywords inside a **single** pair of parentheses.

---

### 2.3.1 Syntax Rules for Combinations

1. **Order:** The order of attributes should follow a logical flow: `{Tempo/Effect} + {Modification Type} + {Remix Info}` _Recommended Order:_ `Extended` &rarr; `Slowed / Sped Up` &rarr; `{Artist} Remix`.
2. **Separator:** Individual keywords within the parentheses must be separated by a **single space**.
3. **Remixer Placement:** If a remix is involved, the format `{Artist} Remix` acts as a single unit within the chain.

---

### 2.3.2 Examples of Combinations

| **Scenario** | **Structure** | ✅ **Correct Example** | ❌ **Incorrect Example** |
| :----------- | :------------ | :--------------------- | :----------------------- |
| **Extended Remix** | Extended + Remix | `Song (Extended DJ Hell Remix)` | `Song (Extended) (FJ Hell Remix)` |
| **Extended & Slowed** | Extended + Slowed | `Song (Extended Slowed)` | `Song (Extended, Slowed)` |
| **Complete Mix** | Extended + Slowed + Remix | `Song (Extended Slowed DJ Hell Remix)` | `Song (Extended Remix by DJ Hell Slowed)` |
| **Sped Up Remix** | Remix + Sped Up | `Song (Sped Up Armin van Buuren Remix)` | `Song (Armin van Buuren Remix Sped Up)` |
| **Acoustic Remix** | Acoustic + Remix | `Song (Acoustic DJ Shadow Remix)` | `Song (Remix Acoustic)` |

> **Rule of Thumb:** Keep it readable. If a combination becomes too long (more than 3 attributes), prioritize the most relevant attribute for the listener (usually `Remix` or `Extended`).

---

## 2.4 Special Cases: Intro & Interlude

Tracks labeled as `Intro` or `Interlude` often do not have a unique "song title" in the traditional sense.

- If the track has a name (e.g., "Welcome to the Show"), use: `Welcome to the Show (Intro)`.
- If the track is unnamed, use the album context or a generic placeholder consistent with the release: `Track 01 (Intro)` or simply `Intro (Interlude)`.
- **Recommendation:** Always try to use the official title if available. Avoid generic titles like `Track 1` unless no other name exists.

---

## 2.5 Common Mistakes

| ❌ **Incorrect** | ✅ **Correct** | **Reason** |
| :--------------- | :------------- | :--------- |
| `Song (Extended Mix) (Remix)` | `Song (Extended Remix)` | Use one pair of parentheses. |
| `Song (feat. Artist)` | `Song` | Features belong in the **Artist** field, not Title (unless part of the official song name). |
| `Song (extended mix)` | `Song (Extended Mix)` | Use Title Case for keywords. |
| `Song - Extended Mix` | `Song (Extended Mix)` | Use parentheses `()`, not hyphens `-`. |
| `Song (DJ Hell ft. Artist Remix)` | `Song (DJ Hell Remix)` | Keep the Remix tag focused on the remixer; features are secondary. |

---

## References

- For rules on how to reflect these versions in the **Filename**, see [01-filename.md](./01-filename.md).
- For rules on defining the **Artist** (and separating remixers), see [03-artist.md](./03-artist.md).

---
