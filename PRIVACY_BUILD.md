# Swype Privacy Edition - Build Notes

## What Was Removed

This privacy-hardened build has **all analytics and tracking code removed** from the original Swype keyboard.

### Removed Components (~4MB):

#### 1. **Analytics SDKs**
- ✅ **Localytics** (3.1MB) - Complete SDK removal
- ✅ **Fabric/Crashlytics** (938KB) - Crash reporting and analytics
- ✅ **Facebook SDK** - All Facebook integration code
- ✅ **Google Ads** - Advertisement components

#### 2. **Manifest Changes**
- Removed `LOCALYTICS_APP_KEY` metadata
- Removed `io.fabric.ApiKey` metadata
- Removed `com.localytics.android.ReferralReceiver`
- Removed Facebook activity declarations
- Removed Google Ads activity declarations

#### 3. **Code Changes**
- Disabled Crashlytics initialization in `IMEApplication.smali`
- Removed all analytics class files from smali code

### What Was Kept

✅ **Core keyboard functionality** - All typing features intact
✅ **Voice input** (Dragon voice recognition)
✅ **Themes and UI mods** (Material Dark, scaling, fonts)
✅ **Word prediction engine** (native libraries)
✅ **SwypeConnect** (cloud sync - can be disabled in settings)
✅ **Language packs**
✅ **In-app purchases** (for themes/languages)

## Privacy Improvements

### Before (Original Swype):
- 28MB APK with 4MB of tracking code
- Connected to: Localytics, Crashlytics, Facebook, Google Analytics
- Analytics initialization on every app start
- Telemetry data collection

### After (Privacy Edition):
- 28MB APK with **zero tracking SDKs**
- No analytics initialization
- No telemetry endpoints
- Clean smali code (70MB decompiled → analytics removed)

## Still Privacy-Sensitive Features

⚠️ **These features are still present but can be disabled:**

1. **SMS/Call Log Scrapers** - Disabled by default, requires opt-in
2. **Social Media Integration** - Twitter/Facebook word learning (opt-in)
3. **SwypeConnect** - Cloud backup (optional)
4. **READ_CONTACTS/READ_SMS permissions** - Deny if not using scraper features

## Installation

```bash
# The signed APK is ready to install
adb install Swype_Privacy_Edition.apk

# Or transfer to your device and install manually
```

## Recommended Settings

After installation, for maximum privacy:

1. **Disable Auto Import Contacts** - Settings → Personalization
2. **Don't use SwypeConnect** - Don't sign in to cloud
3. **Revoke sensitive permissions** - If your ROM allows:
   - READ_SMS
   - READ_CALL_LOG
   - READ_CONTACTS (unless you use the user dictionary)
4. **Use a firewall** (optional) - Block remaining network calls with NetGuard/AFWall+

## Technical Details

- **Original APK**: Swype v3.2.4.3020400 (Black Edition mod)
- **Build tool**: apktool 2.7.0
- **Signing**: Self-signed with RSA 2048-bit key
- **Certificate expires**: 2053-05-13
- **Package name**: `com.nuance.swype.dtc` (unchanged)

## File Checksums

```bash
# APK size
28M Swype_Privacy_Edition.apk

# Verify signature
jarsigner -verify -verbose -certs Swype_Privacy_Edition.apk
```

## Security Notes

⚠️ This is still **decompiled proprietary software** with:
- Closed-source prediction engine (native .so libraries)
- Original Nuance cloud sync capabilities (if enabled)
- SMS/contacts scraping features (if enabled)

**This build only removes third-party tracking**, not all network capabilities.

For maximum privacy:
- Use without network access (offline mode)
- Don't enable personalization features
- Deny all sensitive permissions

## Support

This is a **community privacy build**. Not affiliated with Nuance or the original Black Edition modder.

Original mod: https://4pda.to/forum/index.php?showtopic=150358
This privacy fork: Created 2025-12-26

---

**Use at your own risk. This keyboard was discontinued in 2018. Consider modern open-source alternatives like OpenBoard or FlorisBoard for better long-term privacy.**
