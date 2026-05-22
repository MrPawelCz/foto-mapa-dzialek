# Foto-Mapa Działek

Aplikacja webowa offline do generowania dokumentacji fotograficznej prac na działkach rolnych — do wniosków o płatności obszarowe (ARiMR).

## Co robi

1. Wczytuje zdjęcia z GPS (EXIF) — bezpośrednio w przeglądarce, zdjęcia nie wychodzą poza Twój komputer.
2. Tworzy interaktywną mapę z:
   - ortofotomapą z Geoportalu (z fallbackiem na Esri World Imagery i OpenStreetMap),
   - warstwą działek ewidencyjnych z numerami (KIEG),
   - pinezkami numerowanymi chronologicznie,
   - polilinią pokazującą trasę osoby robiącej zdjęcia.
3. Generuje tabelę z datą i współrzędnymi GPS każdego zdjęcia.
4. Eksportuje dane do XLSX / CSV oraz pozwala wydrukować mapę + tabelę do PDF (A4, gotowe do wniosku).

## Użycie

Otwórz `index.html` w przeglądarce (Chrome / Edge / Firefox) — wszystko działa lokalnie po stronie klienta.

Wersja online (GitHub Pages): zobacz link w opisie repo.

## Wymagania

- Zdjęcia muszą mieć zapisane dane GPS w EXIF (zwykle telefony robią to automatycznie, jeśli lokalizacja jest włączona).
- Połączenie z internetem na czas pobierania kafli mapy (Geoportal/Esri).

## Stos technologiczny

Jeden plik HTML, zero buildu. Biblioteki ładowane z CDN:
- [Leaflet](https://leafletjs.com/) — mapa
- [exifr](https://github.com/MikeKovarik/exifr) — odczyt EXIF
- [SheetJS](https://sheetjs.com/) — eksport XLSX

## Źródła danych

- Ortofotomapa: [Geoportal GUGiK](https://www.geoportal.gov.pl/) (WMS)
- Działki ewidencyjne: [Krajowa Integracja Ewidencji Gruntów](https://integracja.gugik.gov.pl/) (WMS)
