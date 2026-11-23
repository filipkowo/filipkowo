# Plik z wydarzeniami Filipkowa – ściąga

Gra czyta `config.json` (wszyscy gracze) albo `config-test.json` (tylko Ty, w trybie admina: Ustawienia → Tryb admina → „Podgląd pliku testowego”).
Zmiana działa po kilku minutach, bez aktualizacji aplikacji. Najprościej: poproś Claude'a o nowy plik i podmień go na GitHubie.

Daty piszemy w czasie polskim: `"2026-12-06"` (cały dzień) albo `"2026-12-06 18:00"`.
Brak `od` = od zaraz, brak `do` = bez końca.

## prezenty – okienko z prezentem (każdy odbiera raz)
```
{ "id": "mikolajki-2026", "od": "2026-12-06", "do": "2026-12-07",
  "tytul": "Mikołajki!", "tekst": "Z okazji Mikołajek mamy dla Ciebie turbo paczkę!",
  "gwiazdki": 50, "paczka": "turbo", "ile": 1, "seria": "Znicz Kruszyn" }
```
- `id` – unikalna nazwa; ten sam `id` = drugi raz się nie pokaże. Nowy prezent = nowy `id`.
- `paczka`: `podstawowa`, `zwykla`, `duza`, `turbo`; `ile` – ile paczek (1–10); `seria` – opcjonalnie (bez niej dziecko samo wybiera serię).
- Opcjonalnie: `"pilka": "ball_znicz"`, `"stroj": "mama_o2"`.

## sklep – paczka w sklepie na czas, z odliczaniem
```
{ "paczka": "turbo", "od": "2026-12-06", "do": "2026-12-08 20:00", "cena": 150, "napis": "Paczka mikołajkowa" }
```
Turbo paczka jest w sklepie tylko w tym czasie. Dla `zwykla`/`duza` – zmienia cenę (stara przekreślona).

## ogloszenia – okienko bez nagrody (raz)
```
{ "id": "nowe-karty", "tytul": "Nowości!", "tekst": "Wkrótce nowe karty w albumie." }
```

## bonus – mnożnik gwiazdek z gier, z paskiem i odliczaniem w menu
```
{ "od": "2026-12-11 15:00", "do": "2026-12-13", "razy": 2, "napis": "Weekend podwójnych gwiazdek!" }
```
