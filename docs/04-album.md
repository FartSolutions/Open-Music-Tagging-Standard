# 4. Album

This document defines the conventions for the **Album** metadata field. The goal is to ensure consistent grouping of tracks in music players while clearly distinguishing between different release types (Standard, Single, EP, Deluxe, Live).

## 4.1 General Structure

The Album tag must follow this structure: `{Album Name} - {Release Type}`

- **Album Name:** The clear, official title of the album as published by the artist.
- **Separator:** The suffix must be separated by a space, a hyphen, and a space (`-`).
- **Release Type:** An optional suffix indicating the specific nature of the release.

---

### Allowed Release Type Suffixes

|Suffix|Usage|Example
|-|-|-
|_(none)_|Standard full-length albums.|`Let It Be`
|`- Single`|Releases containing 1-3 tracks.|`Blinding Lights - Single`
|`- EP`|Extended Plays (typically 4-6 tracks).|`Future Nostalgia - EP`
|`- Deluxe`|Expanded editions with additional tracks.|`Deep Spectrum - Deluxe`
|`- Live`|Recordings from live performances.|`Let It Be - Live`
|`- Remix`|Standalone albums consisting entirely of remixes.|`Remixes - Remix`

> **Note on Remixes:** Individually remix tracks on a standard album do **not** modify the Album tag. The Album tag only receives a suffix if the entire release is a specific type (e.g., a Remix Album or a Single). For individual remix tracks, the version information belongs in the **Title** tag (e.g., `Song (Remix)`).

---

## 4.2 The "Deluxe" Convention

The `Deluxe` suffix is used for expanded editions of an original album that include bonus tracks, alternate versions, or live recordings alongside the original tracklist.

---

### 4.2.1 Track Numbering Logic

To maintain compatibility with players that sort by Album and Track Number, and to avoid file duplication confusion, Deluxe editions use **interpolated track numbers**.

1. **Original Tracks:** Retain their **original track number** from the standard release.
2. **Bonus Tracks:** Are assigned the **same track number** as the preceding original track.
    - _Logic:_ If a bonus track is conceptually inserted after Track `02`, it also receives the track number `02`.
    - _Result:_ Multiple tracks may share the same track number within a `Deluxe` album. Players typically sort these by Title or file order subsequently.

**Why this approach?**

- **Data Integrity:** It clearly links the bonus track to its context (e.g., a "Deluxe Mix" or "Acoustic Version" of Track 2 follows Track 2).
- **No Gaps:** It avoids confusing gaps in numbering (e.g., 1, 2, 2b, 3) which some players mishandle.
- **Deduplication:** It signals to the user that this track is an _addition_ to the standard flow, not a replacement.

---

### 4.2.2 Examples

**Scenario: "Deep Spectrum" Album**

_Original Release:_ 5 Tracks. _Deluxe Release:_ Adds "Golden Crush" (after Track 2) and "Social Touch" (after Track 4).

**A. Original Album Tags** (_Album Tag:_ `Deep Spectrum`)

|Track #|Title|Album Tag
|-|-|-
|`01`|Love Nightmare|`Deep Spectrum`
|`02`|Deep Spectrum|`Deep Spectrum`
|`03`|Heroic Time|`Deep Spectrum`
|`04`|Global Madness|`Deep Spectrum`
|`05`|Feel Over|`Deep Spectrum`

**B. Deluxe Album Tags** (_Album Tag:_ `Deluxe Spectrum - Deluxe`) _Note how Track 02 and Track 04 appear twice with the same number._

|Track #|Title|Album Tag|Note
|-|-|-|-
|`01`|Love Nightmare|`Deep Spectrum`|Original
|`02`|Deep Spectrum|`Deep Spectrum`|Original
|`02`|Golden Crush|`Deep Spectrum - Deluxe`|**Bonus** (Follows Track 2)
|`03`|Heroic Time|`Deep Spectrum`|Original
|`04`|Global Madness|`Deep Spectrum`|Original
|`04`|Social Touch|`Deep Spectrum - Deluxe`|**Bonus** (Follows Track 4)
|`05`|Feel Over|`Deep Spectrum`|Original

> **Implementation Note:** When tagging files, ensure the `Track Total` (e.g., `05/05`) reflects the _total_ count of files in the original release.

---

## 4.3 Encoding & Characters

- **Character Set:** All UTF-8 characters are permitted.
- **Capitalization:** Must match the official release capitalization.
- **Technical Format:**
    - **MP3:** ID3v2.4 (UTF-8) recommended.
    - **OGG/OPUS/FLAC:** Vorbis Comment (UTF-8).

---

## 4.4 Common Mistakes

|❌ Incorrect|✅ Correct|Reason
|-|-|-
|`Blinding Lights (Single)`|`Blinding Lights - Single`|Use `-` separator.
|`Future Nostaliga (Deluxe Edition)`|`Future Nostalgia - Deluxe`|Keep suffix short and standardized.
|`Deep Spectrum Remixes`|`Deep Spectrum - Remix`|Use standardized suffix for remix albums.
|`02b` (for bonus track)|`02`|Use identical track numbers for interpolation.

---

## References

- For rules on how to format the **Title** tag when versions (Remix, Acoustic, etc.) are involved, see [02-title.md](./02-title.md).
- For rules on **Tack Number** formatting, see [05-dates-tracks.md](./05-dates-tracks.md).

---
