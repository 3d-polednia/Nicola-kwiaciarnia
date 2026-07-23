# Kwiatomania Nicola Cierpisz — strona kwiaciarni

Statyczna strona wizytówka kwiaciarni **Kwiatomania Nicola Cierpisz** w Głubczycach.
Jeden plik `index.html` + zdjęcia w `assets/`. Bez frameworków i build-stepu — otwiera się w przeglądarce i działa na GitHub Pages od razu.

## Zawartość

```
.
├── index.html          # gotowa strona (samodzielna, offline)
├── assets/             # zdjęcia bukietów + logo
├── Kwiatomania.dc.html # edytowalne źródło projektu (Design Component)
└── README.md
```

- `index.html` — **to jest strona.** Publikujesz właśnie ten plik.
- `Kwiatomania.dc.html` — wersja robocza do dalszej edycji w edytorze; wymaga `support.js` i nie jest potrzebna do publikacji.

## Podgląd lokalny

Otwórz `index.html` w przeglądarce, albo:

```bash
python3 -m http.server 8000
# → http://localhost:8000
```

## Publikacja na GitHub Pages

1. Wypchnij repo na GitHub.
2. **Settings → Pages → Build and deployment → Source: „Deploy from a branch"**, branch `main`, folder `/ (root)`.
3. Po chwili strona ruszy pod `https://3d-polednia.github.io/Nicola-kwiaciarnia/`.

## Sekcje strony

Hero · O nas · Galeria · Oferta · Cennik · Program lojalnościowy · Kontakt.

Firma **nie** realizuje dowozów ani oprawy ślubów — te sekcje celowo pominięto.

## Dane firmy

- **Nazwa:** Kwiatomania Nicola Cierpisz
- **Adres:** ul. Fabryczna 7/lok. 3, 48-100 Głubczyce
- **Telefon:** 721 990 041
- **Godziny:** Pon–Pt 9:00–16:00 · Sob 9:00–13:00 · Niedz. nieczynne

---

## Notatki dla Claude Code

**Stack:** czysty HTML + inline CSS. Zero zależności, zero buildu, zero JS (poza `scroll-behavior` w CSS). Wszystkie style są inline; jedyny blok `<style>` w `<head>` trzyma reset, import fontów Google (Cormorant Garamond, Jost, Parisienne, Archivo) i media query mobilną (`max-width:840px`).

**Edycja treści:** teksty, ceny i dane kontaktowe są wpisane wprost w `index.html`. Zdjęcia podmienia się plikami w `assets/` (te same nazwy) lub zmianą `src`.

**Paleta:** szałwiowa zieleń `#33473f`, pudrowy róż `#c98a9b`/`#e6b8c4`, kremowe tło `#faf6f2`/`#f1ebe4`, tło strony `#dfe6e2`.

**Ważne przy zmianach layoutu:** media query dla telefonów celuje w gridy przez selektory atrybutowe (`[style*="grid-template-columns:..."]`). Zmieniając wartości `grid-template-columns` w `index.html`, zaktualizuj też pasujące reguły w bloku `@media(max-width:840px)`, inaczej responsywność się rozjedzie.

**Źródło projektu:** `Kwiatomania.dc.html` to Design Component — jeśli chcesz regenerować `index.html`, przenieś zawartość `<helmet>` do `<head>`, a zawartość między `</helmet>` a `</x-dc>` do `<body>`.
