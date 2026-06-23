# TM-Giga — disztribúció (SideStore / AltStore)

Ez a repó **csak a terjesztést** szolgálja: a Terraforming Mars GIGA companion app
**aláíratlan iOS buildje** (`.ipa`) + a SideStore/AltStore **`source.json`**.
A forráskód külön, privát repóban van.

## SideStore / AltStore source

Add hozzá ezt az URL-t a SideStore-ban (Sources → ➕):

```
https://raw.githubusercontent.com/Vib-R/TM-Giga-dist/main/source.json
```

Ezután az app a SideStore-ban telepíthető, és új build kiadásakor **Update** gombbal frissül.

## Hogyan készül egy új kiadás

1. Unityben (Windows): **TM-Giga ▸ Build iOS Xcode project** → `ios_build/`.
2. A privát repó CI-je lefordítja az **aláíratlan `.ipa`-t** (felhős Mac, GitHub Actions).
3. A `tools/release.ps1` (a privát repóban) feltölti az `.ipa`-t ide egy **Release**-be,
   és frissíti a `source.json` verzióját + linkjét.

> Az `.ipa` **aláíratlan**: a SideStore írja alá az eszközön a saját (ingyenes) Apple ID-ddel.
