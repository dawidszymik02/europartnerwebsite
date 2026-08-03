# Handoff: Strona EURO-PARTNER Tomasz Kozieł (one-page, transport osobowy)

## Overview
Jednostronicowa (one-page) witryna wizerunkowa firmy transportowej **EURO-PARTNER Tomasz Kozieł** — przewóz osób autokarem, busem i mikrobusem, krajowo i międzynarodowo. Cel: zbudować zaufanie (doświadczenie od 2006 r., jakość usług) i doprowadzić użytkownika do kontaktu telefonicznego lub mailowego. Brak formularza — wszystkie CTA to linki `tel:` / `mailto:`.

Struktura scrolla: Nagłówek (sticky) → Hero → O nas → Usługi (3 karty + panel „Nowoczesna flota”) → Dlaczego my → CTA „Zapraszamy do współpracy” → Kontakt/stopka z mapą.

## About the Design Files
Pliki w tym pakiecie są **referencją projektową wykonaną w HTML** — prototypem pokazującym docelowy wygląd i zachowanie, a nie kodem produkcyjnym do wklejenia. Zadaniem jest **odtworzenie tego designu w docelowym środowisku** (Next.js/React, Astro, Vue, WordPress, czysty HTML+CSS — cokolwiek jest w projekcie), korzystając z istniejących w nim wzorców i bibliotek. Jeśli środowiska jeszcze nie ma: dla tej strony w pełni wystarczy statyczny stack (np. Astro albo Next.js z eksportem statycznym, ewentualnie czysty HTML + jeden plik CSS) — strona jest w 100% statyczna, bez logiki serwerowej.

W prototypie style są **inline** (wymóg narzędzia, w którym powstał). W implementacji przenieś je do CSS/Tailwind/CSS-Modules zgodnie z konwencją repo — wartości (kolory, rozmiary, odstępy) muszą zostać zachowane 1:1.

## Fidelity
**High-fidelity.** Kolory, typografia, odstępy, cienie i kopie tekstowe są finalne. Odtwórz UI pixel-perfect. Wszystkie wartości znajdziesz poniżej oraz w `reference/index.html` (samodzielny plik — otwórz w przeglądarce, to jest wzorzec).

## Screens / Views

Jeden widok (`/`), sekcje w kolejności. Kontener treści: `max-width: 1280px; margin: 0 auto`. Poziome paddingi sekcji: `48px` (desktop), `20px` (mobile).

### 1. Header (sticky)
- **Purpose**: nawigacja po sekcjach + stały dostęp do telefonu.
- **Layout**: `position: sticky; top: 0; z-index: 50`, `display:flex; align-items:center; justify-content:space-between`, `padding: 12px 48px`, `background: #2b2b2e` (kolor pobrany pipetą z tła pliku logo — musi się zlewać z logo), `box-shadow: 0 1px 0 rgba(255,255,255,.06)`.
- **Lewa strona**: logo `68×68px`, `object-fit: cover`, `border-radius: 4px`, `display:block`; obok kolumna: „EURO-PARTNER” — Source Serif 4, 21px/600, `#fff`, `letter-spacing:.2px`; pod nim „TOMASZ KOZIEŁ” — IBM Plex Sans, 11px, `#c9a227`, `letter-spacing:1.5px`, `text-transform:uppercase`; `line-height:1.15`, gap 12px.
- **Nawigacja**: `display:flex; align-items:center; gap:34px`. Linki: „O nas” (#o-nas), „Usługi” (#uslugi), „Dlaczego my” (#dlaczego-my), „Kontakt” (#kontakt) — 14.5px, `#e7e5e1`, `white-space:nowrap`, hover `#c9a227`.
- **Przycisk telefonu**: `href="tel:512118720"`, tekst „512 118 720”, `background:#c9a227`, `color:#2b2b2e`, `padding:10px 20px`, `border-radius:3px`, 14px/600, hover `background:#e0b640`.

### 2. Hero
- **Layout**: `position:relative; min-height:640px; display:flex; align-items:center; padding: 0 48px`. Wewnątrz treść `max-width:680px; padding:100px 0; z-index:2`.
- **Tło**: `assets/autokar.jpg` jako `<img>` `position:absolute; inset:0; width/height:100%; object-fit:cover`.
- **Overlay**: `linear-gradient(100deg, rgba(20,20,22,.92) 0%, rgba(20,20,22,.78) 42%, rgba(20,20,22,.42) 78%, rgba(20,20,22,.2) 100%)`.
- **Eyebrow**: kreska `34×1.5px` `#c9a227` + tekst „ZAUFANIE WYMAGAJĄCYCH KLIENTÓW OD 2006 ROKU” — 12.5px/600, `#c9a227`, `letter-spacing:3px`, uppercase; gap 10px, `margin-bottom:22px`.
- **H1**: „Transport osobowy dla wymagających klientów” — Source Serif 4, 50px/600, `line-height:1.14`, `#fff`.
- **Lead**: „Przewóz osób autokarem, busem i mikrobusem — w Polsce i na terenie całej Europy. Bezpiecznie, punktualnie i z niezmiennie wysoką jakością usług, którą wymagający klienci doceniają od 2006 roku.” — 18px, `line-height:1.65`, `#d8d6d1`, `max-width:560px`, `margin-top:24px`.
- **CTA (flex, gap 16px, margin-top 38px, flex-wrap)**:
  - Primary: „Poproś o wycenę” → `mailto:euro.partner@onet.eu?subject=Zapytanie%20o%20wycen%C4%99`; `background:#c9a227; color:#28282b; padding:15px 30px; border-radius:3px; 15px/600`; hover `#e0b640`.
  - Secondary: „Zadzwoń: 512 118 720” → `tel:512118720`; `border:1px solid rgba(255,255,255,.4); color:#fff`, ten sam padding; hover `border-color/#color: #c9a227`.

### 3. O nas (`#o-nas`)
- **Layout**: `padding:120px 48px`, `display:grid; grid-template-columns:1fr 0.86fr; gap:72px; align-items:center; max-width:1280px; margin:0 auto`.
- **Lewa kolumna**: eyebrow „O NAS” (kreska + 12.5px/600 `#a8871f`, letter-spacing 3px, uppercase); H2 „Firma transportowa o ugruntowanej pozycji na rynku” — 34px, `line-height:1.25`, `#1c1c1e`, `margin-bottom:26px`; trzy akapity 16.5px, `line-height:1.8`, `#45443f`, odstęp 18px:
  1. „EURO-PARTNER Tomasz Kozieł to samodzielna firma transportowa o ugruntowanej pozycji na rynku, działająca nieprzerwanie od 2006 roku. Od pierwszego dnia naszym priorytetem jest niezmiennie wysoka jakość usług, pełen profesjonalizm i indywidualne podejście do każdego zlecenia.”
  2. „Dzięki konsekwentnej dbałości o jakość i obsłudze klienta na najwyższym poziomie od lat cieszymy się zaufaniem wymagających klientów — regularnie do nas wracają i polecają nas jako przewoźnika niezawodnego i sprawdzonego.”
  3. „Naszą ofertę kierujemy zarówno do mikro i makro przedsiębiorstw, instytucji, biur podróży, jak i klientów indywidualnych. Do każdej współpracy podchodzimy indywidualnie, a jakość świadczonych usług nieustannie podnosimy dzięki regularnym inwestycjom we flotę pojazdów.”
- **Prawa kolumna**: `assets/bus_srodek.jpg`, `width:100%; height:560px; object-fit:cover; border-radius:4px; box-shadow:0 24px 60px -20px rgba(28,28,30,.35)`.
- **Badge nachodzący na zdjęcie**: `position:absolute; bottom:-24px; left:-24px`, `background:#28282b`, `padding:22px 26px`, `border-radius:4px`, `box-shadow:0 12px 30px -12px rgba(0,0,0,.4)`; „2006” — Source Serif 4, 32px/600, `#c9a227`; pod nim „Ugruntowana pozycja na rynku” — 12.5px, `#cfcdc8`, `letter-spacing:.5px`.

### 4. Usługi (`#uslugi`)
- **Sekcja**: `background:#f1efe9; padding:120px 48px`.
- **Nagłówek wyśrodkowany**: eyebrow „NASZE USŁUGI” z kreskami po obu stronach (`34×1.5px #c9a227`); H2 „Przewóz osób — małe i duże grupy” 34px, `margin-bottom:16px`; lead „Komfortowy i bezpieczny przewóz osób autokarem, busem oraz mikrobusem — na trasach krajowych i na terenie całej Europy.” — 16.5px, `line-height:1.75`, `#55534d`, `max-width:660px; margin:0 auto 64px`.
- **Karty**: `display:grid; grid-template-columns:repeat(3,1fr); gap:32px`. Każda: `background:#fff; border-radius:4px; overflow:hidden; box-shadow:0 10px 30px -18px rgba(28,28,30,.25)`; obraz `height:220px; object-fit:cover`; treść `padding:32px 28px`; kicker 11.5px/600 `#a8871f`, `letter-spacing:2.2px`, uppercase, `margin-bottom:10px`; H3 21px `#1c1c1e`, `margin-bottom:12px`; tekst 15px, `line-height:1.7`, `#55534d`.
  1. `bus-zewnatrz.jpg` · „MAŁE GRUPY” · „Bus i mikrobus” · „Wyjazdy do kilkunastu–dwudziestu osób: delegacje, transfery lotniskowe, wycieczki szkolne i wyjazdy prywatne. W ofercie również wypożyczalnia busów.”
  2. `autokar.jpg` · „DUŻE GRUPY” · „Autokar turystyczny” · „Przewozy dla pełnych grup — biura podróży, firmy, instytucje, kluby sportowe i grupy pielgrzymkowe. Klimatyzacja, przestronny bagażnik, doświadczeni kierowcy.”
  3. `bus_srodek_2.jpg` · „KRAJ I EUROPA” · „Przewozy międzynarodowe” · „Posiadamy odpowiednie uprawnienia do wykonywania międzynarodowego transportu osób. Realizujemy trasy na terenie całej Europy, elastycznie dobierając terminy i przebieg podróży.”
- **Panel „Nowoczesna flota”** (pod kartami, `margin-top:64px`): `display:grid; grid-template-columns:0.95fr 1fr; gap:56px; align-items:center; background:#fff; border-radius:4px; overflow:hidden; box-shadow:0 10px 30px -18px rgba(28,28,30,.25)`. Lewa: `bus_srodek_2.jpg`, `width:100%; height:100%; min-height:360px; object-fit:cover; display:block`. Prawa: `padding:56px 56px 56px 0`; kicker „NOWOCZESNA FLOTA” 12.5px/600 `#a8871f` letter-spacing 2.2px; H3 „Komfort, który widać od pierwszego wejścia” 28px, `line-height:1.3`; tekst 16.5px, `line-height:1.8`, `#55534d`: „Wygodne, klimatyzowane wnętrza i regularne inwestycje w nowe pojazdy — komfort podróży na poziomie, jakiego oczekują wymagający klienci. Każdy autokar i bus przechodzi regularne przeglądy techniczne, a za kierownicą siadają wyłącznie doświadczeni kierowcy.”

### 5. Dlaczego my (`#dlaczego-my`)
- **Layout**: sekcja `padding:120px 48px; max-width:1280px; margin:0 auto`; wewnątrz `display:grid; grid-template-columns:0.86fr 1fr; gap:72px; align-items:center`.
- **Lewa**: `bus_srodek.jpg`, `height:520px; object-fit:cover; border-radius:4px; box-shadow:0 24px 60px -20px rgba(28,28,30,.35)`.
- **Prawa**: eyebrow „DLACZEGO MY”; H2 „Jakość, której wymagający klienci ufają od blisko 20 lat” 34px, `margin-bottom:38px`; siatka atutów `grid-template-columns:1fr 1fr; gap:34px 40px`. Każdy atut: `border-top:2px solid #c9a227; padding-top:16px`; tytuł 17px/600 `#1c1c1e`, `line-height:1.35`, `margin-bottom:8px`; opis 14.5px, `line-height:1.65`, `#55534d`. **Bez numeracji.**
  - Doświadczenie od 2006 roku — Ugruntowana pozycja na rynku transportowym.
  - Nowoczesna flota — Regularne inwestycje w nowe pojazdy.
  - Indywidualne podejście — Do każdego klienta i każdego zlecenia.
  - Uprawnienia międzynarodowe — Przewozy osób w kraju i na terenie całej Europy — elastyczność tras i terminów.
  - Uczciwa współpraca — Przejrzyste warunki i rzetelna wycena.

### 6. CTA „Współpraca”
- `background:#28282b; padding:96px 48px; text-align:center`; kontener `max-width:760px; margin:0 auto`.
- H2 „Zapraszamy do współpracy” 32px `#fff`, `line-height:1.3`, `margin-bottom:22px`.
- Tekst 17px, `line-height:1.75`, `#cfcdc8`, `margin-bottom:38px`: „Gwarantujemy najwyższą jakość usług oraz uczciwe i profesjonalne podejście na każdym etapie realizacji zlecenia. Chętnie udzielimy dodatkowych informacji i przygotujemy indywidualną wycenę dla Państwa potrzeb.”
- Button „Skontaktuj się z nami” → `mailto:euro.partner@onet.eu?subject=Zapytanie%20o%20wsp%C3%B3lprac%C4%99`; `background:#c9a227; color:#28282b; padding:16px 36px; border-radius:3px; 15.5px/600`; hover `#e0b640`.

### 7. Kontakt / stopka (`#kontakt`)
- `background:#1c1c1e; padding:88px 48px 40px; color:#cfcdc8`; grid `1fr 1fr 1.1fr; gap:56px; max-width:1280px`.
- **Kol. 1**: logo `44×44px` `border-radius:6px` + „EURO-PARTNER” (Source Serif 4, 18px/600, `#fff`); adres 14.5px, `line-height:1.7`, `#a9a7a1`: „EURO-PARTNER Tomasz Kozieł / ul. Beskidzka 218, Trzebinia / 34-300 Żywiec”.
- **Kol. 2**: nagłówek „KONTAKT” 12.5px/600 `#c9a227`, letter-spacing 2px; „Tel: 512 118 720” (`tel:512118720`) i „euro.partner@onet.eu” (`mailto:`) — 15px, `line-height:2`, `#e7e5e1`; niżej 12.5px `#8a887f`, `margin-top:26px`: „Uczestnik Ogólnopolskiego Systemu Regionalnej Aktywności Gospodarczej i Społecznej”.
- **Kol. 3**: nagłówek „LOKALIZACJA” + mapa: `<iframe>` OpenStreetMap, `height:190px; border:0; border-radius:4px; filter:grayscale(.3) contrast(1.05); loading="lazy"`, src `https://www.openstreetmap.org/export/embed.html?bbox=19.13%2C49.66%2C19.25%2C49.71&layer=mapnik&marker=49.6845%2C19.1888`. Można podmienić na Google Maps Embed / Leaflet — zachowaj proporcje i lekkie odbarwienie.
- **Belka dolna**: `margin-top:64px; padding-top:26px; border-top:1px solid #333234`, 13px `#7d7b75`, `display:flex; justify-content:space-between; flex-wrap:wrap; gap:10px`: „© {rok} EURO-PARTNER Tomasz Kozieł. Wszelkie prawa zastrzeżone.” + „Transport osobowy krajowy i międzynarodowy · od 2006 roku”.

## Interactions & Behavior
- Nawigacja: linki anchorowe do `#o-nas`, `#uslugi`, `#dlaczego-my`, `#kontakt`. Warto dodać `scroll-behavior:smooth` i `scroll-margin-top: ~92px` na sekcjach (wysokość sticky headera) — w prototypie nie ustawione.
- CTA: wyłącznie `tel:` i `mailto:` (bez formularza, bez backendu). Klient wybrał ten wariant świadomie.
- Hover: linki nav → `#c9a227`; złote przyciski → `#e0b640`; outline button → obramowanie i tekst `#c9a227`. Bez zdefiniowanego transition — dodaj `transition: background-color .18s ease, color .18s ease, border-color .18s ease`.
- Brak stanów loading/error, brak walidacji, brak animacji wejścia (keyframes `fadeUp` zadeklarowany, ale nieużywany — można pominąć lub wykorzystać do subtelnego reveal).
- Focus: prototyp nie definiuje — w implementacji **dodaj widoczny `:focus-visible`** (np. `outline:2px solid #c9a227; outline-offset:2px`).

### Responsive
Jeden breakpoint główny + korekta nawigacji:
- `max-width:1040px`: nav `gap:22px`, linki `font-size:13.5px` (żeby „Dlaczego my” nie łamało się na dwie linie; linki mają `white-space:nowrap`).
- `max-width:820px` (mobile):
  - header `padding:10px 18px`, nav `gap:14px`, **wszystkie linki nav ukryte oprócz przycisku z telefonem** (`a:not(:last-child){display:none}`). Jeśli w docelowej implementacji chcecie hamburger menu — to rozszerzenie, wymaga zatwierdzenia u klienta.
  - hero: `padding:0 20px`, `min-height:520px`, treść `padding:80px 0 64px`, H1 `32px`.
  - „O nas” i „Dlaczego my”: 1 kolumna, `gap:40px`; sekcja „O nas” `padding:64px 20px`; zdjęcia odpowiednio `340px` / `280px`.
  - sekcje z `padding:120px 48px` → `64px 20px`; wszystkie gridy (karty, panel flota, atuty, stopka) → 1 kolumna; panel flota `gap:0`, obraz `240px`, tekst `padding:32px 24px 40px`; atuty `gap:24px`; stopka `padding:56px 20px 32px`, belka dolna w kolumnie; wszystkie `h2` → `26px`.

## State Management
Brak. Strona statyczna, bez stanu i bez fetchowania danych. Jedyna „dynamika”: rok w stopce (`new Date().getFullYear()`) — może być statyczny lub renderowany po stronie builda. Treść atutów w prototypie jest tablicą 5 obiektów `{title, desc}` — w implementacji można trzymać jako dane (JSON/CMS) lub statyczny markup.

## Design Tokens

**Kolory**
| Token | Hex | Użycie |
|---|---|---|
| Tło strony | `#faf8f4` | body |
| Tło sekcji alternatywne | `#f1efe9` | sekcja Usługi |
| Karty | `#ffffff` | karty usług, panel flota |
| Grafit nagłówka | `#2b2b2e` | sticky header (= tło pliku logo) |
| Grafit sekcji | `#28282b` | badge „2006”, CTA band |
| Grafit stopki | `#1c1c1e` | footer, główny kolor tekstu |
| Złoty (akcent) | `#c9a227` | przyciski, kreski, eyebrow na ciemnym |
| Złoty hover | `#e0b640` | hover przycisków |
| Złoty ciemniejszy | `#a8871f` | eyebrow na jasnym tle, hover linków |
| Tekst body | `#45443f` | akapity O nas |
| Tekst pomocniczy | `#55534d` | opisy kart/atutów |
| Tekst na ciemnym | `#e7e5e1`, `#d8d6d1`, `#cfcdc8`, `#a9a7a1`, `#8a887f`, `#7d7b75` | nav, lead hero, CTA, stopka |
| Linie | `#e8e5dd` (jasne), `#333234` (stopka) | separatory |

**Typografia** (Google Fonts): `Source Serif 4` (500/600/700) — nagłówki H1–H3, liczba „2006”, wordmark; `IBM Plex Sans` (400/500/600) — reszta. Fallbacki: `Georgia, serif` i `system-ui, sans-serif`.
Skala: 50 / 34 / 32 / 28 / 21 / 18 / 17 / 16.5 / 15.5 / 15 / 14.5 / 13 / 12.5 / 11.5 / 11 px. Line-height: nagłówki 1.14–1.35, tekst 1.65–1.8. Letter-spacing: eyebrow 2–3px uppercase, wordmark .2px.

**Spacing**: 8 / 10 / 12 / 16 / 18 / 22 / 24 / 26 / 32 / 34 / 38 / 40 / 56 / 64 / 72 / 96 / 120 px. Sekcje desktop `120px` w pionie (CTA `96px`, stopka `88px`), mobile `64px`.

**Border radius**: `3px` (przyciski), `4px` (karty, zdjęcia, logo w headerze, mapa), `6px` (logo w stopce).

**Shadows**: karty `0 10px 30px -18px rgba(28,28,30,.25)`; duże zdjęcia `0 24px 60px -20px rgba(28,28,30,.35)`; badge `0 12px 30px -12px rgba(0,0,0,.4)`; header `0 1px 0 rgba(255,255,255,.06)`.

## Assets
Zdjęcia dostarczone przez klienta (w `reference/assets/`):
- `euro-partner-logo.png` — 1440×1440, logo na nieprzezroczystym grafitowym tle `#2b2b2e`. **Dlatego tło headera ma dokładnie ten kolor.** Warto poprosić klienta o wersję z przezroczystym tłem / wektor (SVG) — wtedy header może dostać dowolne tło.
- `autokar.jpg` — 960×540, autokar (hero + karta „Autokar turystyczny”).
- `bus-zewnatrz.jpg` — 206×206, bus z zewnątrz. **Niska rozdzielczość** — użyty w karcie 220px wysokości; przy większym kadrze będzie miękki. Poprosić klienta o oryginał.
- `bus_srodek.jpg` — 720×960, wnętrze autokaru (O nas, Dlaczego my).
- `bus_srodek_2.jpg` — 206×206, wnętrze busa (karta międzynarodowa + panel „Nowoczesna flota”). Również niska rozdzielczość.

Brak ikon i grafik wektorowych — akcenty to zwykłe kreski (`div`/`span` 34×1.5px). Nie dodawać ikon bez zgody klienta.

Do zrobienia w implementacji: `alt` texty (są w prototypie), `<title>`, meta description, Open Graph, favicon z logo, oraz optymalizacja obrazów (WebP/AVIF + `loading="lazy"` poza hero, `width`/`height` dla CLS).

## Files
- `reference/index.html` — **wzorzec 1:1**: samodzielna, statyczna wersja strony (inline style + jeden blok `<style>` z media queries i hoverami). Otwórz w przeglądarce i porównuj implementację z tym plikiem.
- `reference/assets/*` — zdjęcia i logo.
- `prototype/Euro-Partner.dc.html` — oryginalny prototyp z narzędzia projektowego (wymaga runtime'u narzędzia; traktować jako źródło historyczne, nie do uruchamiania).

## Suggested prompt for Claude Code
> W tym repo zaimplementuj stronę EURO-PARTNER zgodnie z `design_handoff_euro_partner_site/README.md`. Wzorcem 1:1 jest `reference/index.html` — odtwórz go pixel-perfect w naszym stacku (komponenty + CSS zgodnie z konwencjami repo, style nie inline), zachowując wszystkie kolory, rozmiary, odstępy, cienie i teksty. Skopiuj zdjęcia z `reference/assets/`, zoptymalizuj je, dodaj `focus-visible`, `scroll-margin-top` pod sticky header, transition na hoverach oraz meta/OG/favicon. Zachowaj responsywność opisaną w sekcji Responsive (breakpointy 1040px i 820px).
