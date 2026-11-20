# Football Training – anglická verze aplikace pro Android TV

Tohle je hotový projekt. Z něj GitHub sám sestaví instalační soubor `app-debug.apk`.
Nic se nemusí instalovat do počítače.

## 1) Sestavení APK (jednou, potom už jen při změnách)
1. Založ si účet na github.com (zdarma) a vytvoř nový repozitář. Nech ho **Private** (v aplikaci jsou fotky hráčů).
2. Nahraj do něj všechny soubory z tohoto projektu (v repozitáři klikni na *Add file → Upload files* a přetáhni obsah složky).
   Důležité: musí se nahrát i složka **.github** (je skrytá, v Průzkumníku zapni zobrazení skrytých souborů).
   Kdyby se nenahrála: *Add file → Create new file*, jako název napiš `.github/workflows/build.yml` a vlož obsah z toho souboru.
3. Otevři záložku **Actions**. Sestavení se spustí samo (nebo *Build APK → Run workflow*). Trvá asi 5–10 minut.
4. Po dokončení otevři běh sestavení a dole v části **Artifacts** stáhni `football-training-apk`. V zipu je `app-debug.apk`.

## 2) Dostání APK do televize (vyber jednu cestu)
**A) Flash disk (nejjednodušší)**
1. Zkopíruj `app-debug.apk` na flash disk a připoj ho k TV.
2. V TV nainstaluj správce souborů (např. *File Commander* nebo *X-plore*) z Google Play.
3. V nastavení TV povol tomuto správci instalaci z neznámých zdrojů (*Nastavení → Zabezpečení → Neznámé zdroje*, názvy se liší podle TV).
4. Ve správci souborů otevři APK a potvrď instalaci.

**B) Aplikace Send Files to TV**
Nainstaluj *Send Files to TV* do TV i do telefonu (nebo počítače), obě zařízení musí být na stejné Wi‑Fi. Pošli APK a v TV ho otevři.

**C) ADB přes Wi‑Fi (pro zkušenější)**
V TV zapni *Možnosti pro vývojáře → Ladění přes USB/síť* a spusť na počítači:
`adb connect IP_ADRESA_TV:5555` a pak `adb install app-debug.apk`

Aplikace se v TV objeví na domovské obrazovce mezi aplikacemi s názvem *Football Training*.

## 3) Aktualizace aplikace
Až dostaneš nový soubor `index.html`, v repozitáři otevři `www/index.html`, zvol *Edit* (tužka) nebo *Upload* a nahraď ho. GitHub sám sestaví nové APK. Instalaci pak proveď znovu stejným způsobem (přes starou verzi, data hráčů zůstanou).

## Poznámky
- Hlas používá systémový hlas TV. Anglický hlas musí být v TV nainstalovaný (*Nastavení → Systém → Jazyk → Převod textu na řeč*).
- Je to ladicí (debug) APK. Pro osobní použití to stačí, do Google Play se takhle nedává.
