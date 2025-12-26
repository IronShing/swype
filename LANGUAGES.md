# Included Languages

The `swype_last` variant (Black Edition base) includes only **4 languages** by default:

## Included:
- ✅ **English** (US/UK/UN) - `ENubUN_xt9_ALM3.ldb.mp3` (4.2MB)
- ✅ **Chinese Simplified** (China) - `Chinese_CN.msdb.mp3`
- ✅ **Chinese Traditional** (Taiwan) - `Chinese_TW.msdb.mp3`
- ✅ **Chinese Traditional** (Hong Kong) - `Chinese_HK.msdb.mp3`

## Not Included:
This variant does **NOT** include additional language packs like:
- Spanish, French, German, Italian, Portuguese
- Russian, Arabic, Hindi, Japanese, Korean
- Nordic languages (Swedish, Danish, Norwegian, Finnish)
- And 50+ other languages from the full Swype versions

## Why So Few Languages?

The `swype_last` directory appears to be a **minimal English + Chinese variant**, possibly:
- From a specific OEM build (Chinese market phones)
- Stripped down to reduce size
- Or the base decompiled version before language packs

## Other Variants in This Repo:

### com.nuance.swype.dtc.india/ (11+ languages):
Indian subcontinent languages:
- Hindi (HI), Konkani (KOK), Kashmiri (KS)
- Dogri (DOI), Maithili (MAI), Manipuri (MNI)
- Sanskrit (SAT), Santali (SA), Sindhi (SD)
- Bodo (BRX)
- Plus: English, Chinese (3 variants)

### com.nuance.swype.oppo/ (20+ languages):
International variant:
- **European**: French (FR), Spanish (ES), Turkish (TR)
- **Asian**: Arabic (AR), Bengali (BN), Hindi (HI), Indonesian (ID), Malay (MS), Myanmar (MY), Sinhala (SI), Swahili (SW), Tamil (TA), Telugu (TE), Thai (TH), Urdu (UR), Vietnamese (VI), Tagalog/Filipino (TL)
- **Persian**: Farsi (FA)
- **Chinese**: Simplified with Pinyin (ZH)
- Plus: English

### com.nuance.swype.dtc/
Empty or minimal variant

## Adding More Languages:

To add languages, you would need:
1. Original `.ldb` or `.msdb` language pack files from full Swype APK
2. Copy them to `swype_last/assets/`
3. Update `assets/languagelist_supported.xml`
4. Rebuild with `apktool b swype_last`

Language packs can be extracted from:
- Full Swype APK (if you have it)
- Other decompiled variants in this repo
- Swype language pack downloads (if still available)

## Current Build:

The **Privacy Edition** APK includes exactly what was in `swype_last`:
- English (primary)
- Chinese variants (3)

If you need more languages, let me know which ones and I can check if they're in the other variants (`dtc.india` or `oppo`).
