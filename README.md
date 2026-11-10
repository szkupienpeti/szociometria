# Szociometria

Egyszerű, kliensoldali szociometria-kiértékelő: névsor, kérdések, válaszok rögzítése, majd kérdésenként
strigulás, mátrix és szociogram. Élő változat: https://szkupien.hu/szociometria/

- Az egész alkalmazás egyetlen `index.html` (sima HTML/CSS/JS, függőség és build nélkül).
- Az adatok csak a böngésző `localStorage`-ában vannak; mentés és átvitel az **Adatok** fülön JSON exporttal/importtal.
- Az exportált fájlok a gyerekek nevét tartalmazzák, ezért a `.gitignore` kizárja őket (`szociometria-*.json`).

## Hostolás

GitHub Pages, a `main` ág gyökeréből (Settings → Pages → Deploy from a branch → `main` / `/`).
A `szkupien.hu` domain a `szkupienpeti.github.io` repóhoz tartozik, így ez a repo automatikusan a
`/szociometria/` útvonalon jelenik meg. A `.nojekyll` kikapcsolja a Jekyll-feldolgozást.

## Adatformátum

```json
{
  "version": 1,
  "title": "5.b – 2026 ősz",
  "children": [{ "id": 1, "name": "Kiss Anna" }],
  "questions": [{ "id": 1, "text": "Kivel ülnél egy padban?", "category": "rokonszenv", "count": 3 }],
  "answers": { "1": { "1": [2, 5, 7] } }
}
```

`answers`: válaszadó gyerek id → kérdés id → a választott gyerekek id-i, a választás sorrendjében.
