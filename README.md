# snidl-dane

Dane do laboratoriów z przedmiotu „Sieci neuronowe i deep learning”. Pliki są publikowane jako
załączniki release'ów; notatniki pobierają je automatycznie przy pierwszym uruchomieniu.

## n03-v1 — Oxford-IIIT Pet 160×160 (notatnik N03, transfer learning)

Plik: `snidl_n03_oxford_pets_160.zip` (ok. 68 MB)
SHA-256: `a0c0bd683d35aac28b279feed29288fc8f30c22c89d1a4d58c79f6b61e4bf4f1`

Zawartość katalogu `oxford_pets_160/`:

- `images/` — 7335 zdjęć RGB 160×160 (JPEG), 37 ras psów i kotów;
- `masks/` — trimapy 160×160 (PNG: 1 = zwierzę, 2 = tło, 3 = brzeg);
- `metadata.csv` — plik, rasa, numer klasy, gatunek, podział (train 2939 / val 734 / test 3662)
  oraz ramka zwierzęcia `x_min, y_min, x_max, y_max` jako ułamki szerokości i wysokości obrazu;
- `README.md` — szczegóły przygotowania.

Notatnik szuka danych kolejno w `~/.cache/snidl` (lub katalogu wskazanym zmienną `SNIDL_DATA`),
`dane/`, `../dane/` i `../../laboratoria/dane/`. Jeśli ich nie znajdzie, pobiera zip, sprawdza
sumę SHA-256 i rozpakowuje go do `~/.cache/snidl`.

### Źródło i licencja

O. M. Parkhi, A. Vedaldi, A. Zisserman, C. V. Jawahar, „Cats and Dogs”, IEEE CVPR 2012,
https://www.robots.ox.ac.uk/~vgg/data/pets/

Oryginał jest udostępniony na licencji Creative Commons Attribution-ShareAlike 4.0 International
(CC BY-SA 4.0). Ta przetworzona wersja jest udostępniana na tej samej licencji:
https://creativecommons.org/licenses/by-sa/4.0/

Zmiany względem oryginału: przeskalowanie do 160×160 bez zachowania proporcji, konwersja do RGB JPEG,
wyznaczenie ramek z trimap (bez drobnych odłączonych fragmentów), nowy podział train/val
(warstwowo 80/20 z oficjalnego trainval, ziarno 2026), oficjalny test bez zmian. Pominięto 14 obrazów
z trimapami bez zaznaczonego zwierzęcia.
