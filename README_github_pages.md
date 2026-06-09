# NZÚ 2026 — Znalostní báze (web)

Jednoduchá statická webová aplikace pro sdílení znalostní báze o programu Nová zelená úsporám 2026.

## Struktura

```
03_web/
├── index.html          ← shell aplikace (HTML + CSS + JS, vše v jednom souboru)
└── content/            ← zdrojové .md soubory (obsah znalostní báze)
    ├── 00_prehled_programu.md
    ├── 01_nzu_light.md
    ├── 02_uver_rodinne_domy.md
    ├── 03_uver_bytove_domy.md
    ├── 04_castky_a_parametry.md
    ├── 05_proces_zadosti_a_dokumenty.md
    ├── 06_zpusobilost_kombinace_terminy.md
    ├── 07_renovacni_pas_poradenstvi.md
    ├── 08_faq.md
    ├── 09_pojmy_zkratky.md
    └── 10_zdroje.md
```

## Jak aktualizovat obsah

Edituj přímo soubory v `content/` a pushni na GitHub. Web se automaticky aktualizuje.

## Jak přidat novou sekci

1. Vytvoř nový soubor v `content/`, např. `11_nova_sekce.md`
2. V `index.html` přidej do pole `PAGES` (řádek ~140): `'11_nova_sekce'`
3. Přidej popisek do `PAGE_LABELS` (řádek ~155): `'11_nova_sekce': 'Název sekce'`
4. Přidej tlačítko do navigace (HTML sekce `<nav id="sidebar">`)
5. Pushni — hotovo.

## Nasazení na GitHub Pages

1. Vytvoř nový GitHub repozitář (např. `nzu-2026`)
2. Nahraj obsah složky `03_web/` do kořene repozitáře
3. V repozitáři jdi na **Settings → Pages**
4. Zvol **Deploy from a branch → main → / (root)**
5. Ulož → za chvíli dostaneš URL ve tvaru `https://uzivatel.github.io/nzu-2026/`

## Poznámky

- Aplikace funguje čistě staticky — žádný backend, žádné závislosti kromě `marked.js` (CDN)
- Vyhledávání je klientské — funguje přes všechny sekce najednou
- FAQ sekce (`08_faq.md`) se renderuje jako rozbalovací accordion
- `⚠` varování jsou automaticky zvýrazněna oranžovým badge
- `[[soubor_id]]` cross-reference jsou automaticky převedeny na navigační odkazy
