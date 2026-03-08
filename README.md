# MEBLE.PRO Konfigurator — Android APK

## Struktura plików
```
meble_apk/
├── index.html          ← główna aplikacja
├── manifest.json       ← PWA manifest
├── sw.js               ← Service Worker (offline)
├── capacitor.config.json
├── package.json
├── icons/
│   ├── icon-48.png
│   ├── icon-192.png
│   └── icon-512.png
└── README.md
```

## Opcja A — Najprostsza: PWA lokalnie (bez serwera)

Otwórz `index.html` w przeglądarce Chrome na telefonie.
Na Android: Menu → "Dodaj do ekranu głównego" → działa jak apka.

**WAŻNE:** Aby Service Worker i offline działały — potrzebny jest HTTPS lub localhost.
Użyj opcji B lub C dla pełnego offline APK.

---

## Opcja B — Prawdziwy APK przez Capacitor

### Wymagania
- Node.js 18+ → https://nodejs.org
- Android Studio → https://developer.android.com/studio
- Java 17 (JDK) → instaluje się z Android Studio

### Kroki

**1. Zainstaluj zależności**
```bash
cd meble_apk
npm install
```

**2. Dodaj platformę Android**
```bash
npx cap add android
npx cap sync android
```

**3. Otwórz w Android Studio**
```bash
npx cap open android
```

**4. W Android Studio:**
- Build → Generate Signed Bundle / APK
- Wybierz APK
- Utwórz keystore (podpisywanie)
- Build Release APK

**5. APK znajdziesz w:**
```
android/app/build/outputs/apk/release/app-release.apk
```

---

## Opcja C — Online builder (bez instalacji)

1. Wgraj `index.html` + pliki na GitHub Pages lub Netlify (bezpłatne)
2. Wejdź na: https://www.pwabuilder.com
3. Wklej URL swojej strony
4. Kliknij "Package for stores" → Android APK
5. Pobierz gotowy APK

---

## Funkcje offline
- ✅ Cały konfigurator działa bez internetu
- ✅ BOM, rozkrój, szpargalka wiercenia
- ✅ Zapis projektów (localStorage)
- ⚠️ Czcionki Google Fonts — przy pierwszym uruchomieniu potrzebny internet
  (potem są w cache)
- ⚠️ Three.js 3D widok — j.w.

---

## Wersja
- App: 3.2.0
- Systemy szuflad: Blum Antaro/Tandembox/Merivobox/Legrabox,
  Hettich InnoTech/ArciTech, Grass Vionaro/Nova Pro/Dynapro,
  GTV Axis Pro/Vertico, DTC Mova/Slimbox
