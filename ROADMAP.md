# Pohybové aktivity — Dětská léčebna Křetín

## Struktura projektu

```
aktivity/
├── v1/                  ← záloha původní verze
│   ├── index.html
│   └── ROADMAP.md
├── index.html           ← v2 (aktuální)
└── ROADMAP.md           ← tento soubor
```

## v1.0 (záloha v `v1/`)

- [x] Registrace, přihlášení (PIN)
- [x] Dashboard, záznam aktivit (pevný seznam), záznam km
- [x] Žebříček, srovnání skupin/podskupin
- [x] Admin panel (základní správa dětí, export)
- [x] 1 aktivita denně, 60min okno na opravu, km uzávěrka 21:00

## v2.0 (aktuální)

### Datový model
- [x] **Vychovatelky** — správa vychovatelek
- [x] **Lokace** — tělocvična, hřiště, hala, bazén, park, okolí (konfigurovatelné)
- [x] **Denní rozvrh** — admin vybírá, které vychovatelky dnes pracují a které aktivity probíhají
- [x] **Kapacita** — každá aktivita má max počet dětí (např. jumping=6, discgolf=10)
- [x] **Konfigurovatelné nastavení** — admin heslo, km uzávěrka, cancel window, skupiny, podskupiny
- [ ] **Globální katalog aktivit** — aktivity se definují jednou a přiřazují vychovatelkám

### Dětská část (6 obrazovek)
- [x] **Registrace/Přihlášení** — dynamické skupiny/podskupiny z nastavení
- [x] **Dashboard** — přehled + dnešní nabídka aktivit s kapacitou
- [x] **Záznam aktivit** — zobrazuje rozvrh na všechny naplánované dny, viditelná kapacita, plné aktivity zamčené
- [x] **Záznam km** — beze změny (uzávěrka konfigurovatelná)
- [x] **Žebříček** — beze změny (dynamické filtry dle skupin)
- [x] **Profily** — beze změny

### Admin panel (6 záložek)
- [x] **Program** — přehled celého běhu (programStart/programEnd), denní dlaždice ve dvou variantách (scrollovací pás / mřížka), výběr dne kliknutím, detail dne s výběrem vychovatelek, inline chipy aktivit, kontrola konfliktu lokací, detailní přehled obsazenosti (aktivita + vychovatelka + přihlášené děti s avatary + nepřihlášené děti), širší admin layout (960px)
- [ ] **Aktivity** — globální katalog aktivit (název, body, ikona, lokace, max dětí), sdílený mezi vychovatelkami
- [x] **Vychovatelky** — CRUD vychovatelek, přiřazení aktivit z katalogu (chipy místo checkboxů, seskupené podle bodů)
- [x] **Správa dětí** — seznam, přidání/úprava/smazání, zpětné zapisování záznamů
- [x] **Statistiky** — celkový přehled, graf aktivity v čase, porovnání skupin, nejoblíbenější aktivity, export JSON
- [x] **Nastavení** — správa lokací, skupiny/podskupiny, admin heslo, km uzávěrka, cancel window

### Hosting & data
- [x] **GitHub Pages** — https://dana-mar-77.github.io/aktivity/
- [x] **Supabase** — sdílená databáze (realtime sync mezi prohlížeči)
- [x] **localStorage** — fallback cache

### Klíčová pravidla
- 1 aktivita denně (z rozvrhu)
- Změna aktivity nejpozději 30 min před začátkem (dle timeSlotu v rozvrhu, konfigurovatelné)
- Km uzávěrka ve 21:00 (konfigurovatelné)
- Kontrola konfliktu lokací (varování, neblokuje)
- Kapacitní limit — plné aktivity nelze vybrat
- localStorage klíč: `kretin_v2` (nezávislé na v1)

## Možná vylepšení (v3.0+)

- [ ] Animace při získání bodů
- [ ] Odznaky/achievementy za milníky
- [ ] Streak — počet dní po sobě s aktivitou
- [ ] Import dat z JSON
- [ ] Tisk žebříčku / certifikátů
- [ ] PWA (offline podpora, ikona na ploše)
- [ ] Více časových slotů za den (13:30–14:30 + 15:00–16:00)
- [ ] Fotogalerie aktivit
