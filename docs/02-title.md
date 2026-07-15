# 2. Title

This document defines the conventions for **Title** metadata field. The goal is to ensure that song titles are displayed consistently across all players while clearly indicating specific versions, mixes, or edits.

## 2.1 General Structure

The Title tag must follow this structure: `{Base Title} {Version Suffix}`

- **Base:** The clear, official title of the song as published by the artist.
- **Version Suffix:** Optional. If present, it must be enclosed in parenthesees `()` and placed immediately after the base title, separated by a single space.
- **Character Set:** All UTF-8 characters are allowed.
- **Capitalization:** Must match the official capitalization of the base title. Version keywords inside the parentheses follow **Title Case** (e.g., `Extended Mix`, not `extended mix`), unless the artist specifically stylizes them otherwise.

## 2.2 Allowed Version Keywords

The following keywords are standardized for use within the parentheses. Do not invent new keywords; if a version does not fit, use the closest matching standard term.

|**Keyword**|**Usage**|**Example**
|-|-|-
|`Extended Mix`|Club or extended versions with longer intros/outros.|`Song (Extended Mix)`
|`Remix`|A remix by another artist. Requires the remixer's name.|`Song (Artist Remix)`
|`Acoustic`|Stripped-down, unplugged versions.|`Song (Acoustic)`
|`Instrumental`|Versions without vocals.|`Song (Instrumental)`
|`Orchestral`|Versions performed by an orchestra.|`Song (Orchestral)`
|`Live`|Live recording. Optionally includes location/year.|`Song (Live)` or `Song (Live at Wembley 1985)`
|`Slowed`|Slowed down tempo (often with reverb).|`Song (Slowed)`
|`Sped Up`|Increased tempo (nightcore style).|`Song (Sped Up)`
|`Intro`|Tracks serving as an introduction.|`Song (Intro)`
|`Interlude`|Short connection tracks.|`Song (Interlude)`
|`Radio Edit`|Shortened version for radio play.|`Song (Radio Edit)`
|`VIP`|"Variation In Production" (common in Drum & Bass/Dubstep).|`Song (VIP)`
