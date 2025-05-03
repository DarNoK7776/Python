# GIT - academy

## Ćwiczenia lokalne
Przed przystąpieniem do ćwiczeń wstępnie skonfiguruj Git za pomocą instrukcji Linux -> Git
### Przygotowanie repozytorium
Przygotuj katalog na repozytorium lokalne
```
mkdir ~/workspace/planes
cd ~/workspace/planes
```
Zainicjuj repozytorium
```
git init
```
### Operacje w repozytorium
Stwórz pusty plik template.md
```
touch template.md
```
dodaj go do repozytorium
```
git add template.md
```
Zacommituj dodany plik
```
git commit -m "Dodano plik template.md"
```
Sprawdź stan za pomocą komendy
```
git status
```
drugie polecenie
```
git log --oneline --graph --all
```
Dodaj treść do pliku template.md
```
nano template.md
```
treść
```
# producent - model
+ Ilość pasażerów: xyz
+ Zasięg: xyz
+ Długość: xyz
+ Silniki: xyz
```
Zacommituj zmodyfikowany plik
```
git add .
git commit -m "Dodano zawartość do pliku template.md"
```
Sprawdź stan
```
git log --oneline --graph --all
```
Spodziewany wynik
```
* bb6569f (HEAD -> master) Dodano zawartość do pliku template.md
* 8c9e9ec Dodano plik template.md
```
Popraw plik template.md
```
nano template.md
```
treść
```
# producent - model
+ Ilość pasażerów: xyz
+ Zasięg: xyz
+ Długość: xyz
+ Silniki: x
```
Zacommituj zmodyfikowany plik
```
git add .
git commit -m "Poprawiono zawartość do pliku template.md"
```
Sprawdź stan
```
git log --oneline --graph --all
```
Spodziewany wynik
```
* 2444573 (HEAD -> master) Poprawiono zawartość do pliku template.md
* bb6569f Dodano zawartość do pliku template.md
* 8c9e9ec Dodano plik template.md
```
Zmień nazwę pliku w repozytorium z template.md na template_new.md
```
git mv template.md template_new.md
```
Wyświetl status
```
git status
```
Spodziewany wynik
```
Na gałęzi master
Zmiany do złożenia:
  (użyj „git restore --staged <plik>...”, aby wycofać)
	zmieniono nazwę: template.md -> template_new.md
```
zrób commit
```
git add .
git commit -m "Zmieniono nazwę pliku"
```
Wyświetl status
```
git status
```
Spodziewany wynik
```
Na gałęzi master
nic do złożenia, drzewo robocze czyste
```
Sprawdź stan
```
git log --oneline --graph --all
```
Spodziewany wynik
```
* dfa21b4 (HEAD -> master) Zmieniono nazwę pliku
* 2444573 Poprawiono zawartość do pliku template.md
* bb6569f Dodano zawartość do pliku template.md
* 8c9e9ec Dodano plik template.md
```
### Praca z gałęziami
Zrób branch boeing i się na nią przełącz
```
git branch boeing
git checkout boeing
```
Skopiuj plik temlate_new.md do 737.md
```
cp template_new.md 737.md
```
I zmień go według wzoru
```
# Boeing - 737 MAX 8
+ Ilość pasażerów: 210
+ Zasięg: 6570
+ Długość: 39
+ Silniki: 2
```
Skopiuj plik template_new.md do 777.md
```
cp template_new.md 777.md
```
I zmień go według wzoru
```
# Boeing - 777-300ER 
+ Ilość pasażerów: 451
+ Zasięg: 13650
+ Długość: 74 
+ Silniki: 2
```
Dodaj plik i zrób commit
```
git add .
git commit -m "Dodano 737.md i 777.md"
```
Przełącz na branch master
```
git checkout master
```
Zauważ, że w katalogu znajduje się tylko plik template_new.md

Zmodyfikuj plik template_new.md według wzoru
```
# producent - model
+ Ilość pasażerów: xyz
+ Zasięg: xyz xyz
+ Długość: xyz
+ Silniki: x
```
Zrób commit
```
git add .
git commit -m "Zmodyfikowano template_new.md"
```
Sprawdź stan
```
git log --oneline --graph --all
```
przełącz się na branch boeing, dodaj plik 787.md i go zacommituj

```
git checkout boeing
cp template_new.md 787.md
git add .
git commit -m "Dodano 787.md"
```
Zmerguj branch boeing do master
```
git checkout master
git merge boeing

```
Podaj powód mergowania
```
Merge branch 'boeing' - koniec prac na gałęzi
```
wynik polecenia
```
Merge made by the 'ort' strategy.
 737.md | 5 +++++
 777.md | 5 +++++
 787.md | 5 +++++
 3 files changed, 15 insertions(+)
 create mode 100644 737.md
 create mode 100644 777.md
 create mode 100644 787.md
```
Sprawdź stan
```
git log --oneline --graph --all
```
Spodziewany wynik
```
*   3ce663d (HEAD -> master) Merge branch 'boeing' - koniec prac na gałęzi
|\  
| * 773adb2 (boeing) Dodano 787.md
| * 960e963 Dodano 737.md i 777.md
* | 63a1084 Zmodyfikowano template_new.md
|/  
* dfa21b4 Zmieniono nazwę pliku
* 2444573 Poprawiono zawartość do pliku template.md
* bb6569f Dodano zawartość do pliku template.md
* 8c9e9ec Dodano plik template.md
```
Przełączanie się na danego commita
```
git checkout dfa21b4
```
Zauważ, że po przełączeniu dostępny jest tylko plik template_new.md
## Ćwiczenia zdalne
Załóż repozytorium na [https://github.com]
Skonfiguruj połączenie Git

### Klonowanie repozytorium
```
cd ~/workspace
git clone git@github.com:user/planes.git
cd planes
```

### Operacje w repozytorium
Stwórz pusty plik template.md
```
touch template.md
```
dodaj go do repozytorium
```
git add template.md
```
Zacommituj dodany plik
```
git commit -m "Dodano plik template.md"
```
Sprawdź stan za pomocą komendy
```
git status
```
drugie polecenie
```
git log --oneline --graph --all
```
Wypchnij do github
```
git push
```

Dodaj treść do pliku template.md
```
nano template.md
```
treść
```
# producent - model
+ Ilość pasażerów: xyz
+ Zasięg: xyz
+ Długość: xyz
+ Silniki: xyz
```
Zacommituj zmodyfikowany plik
```
git add .
git commit -m "Dodano zawartość do pliku template.md"
```
Wypchnij do github
```
git push
```
Sprawdź stan na github
### Praca z gałęziami
Zrób branch boeing i się na nią przełącz
```
git branch boeing
git checkout boeing
```
Skopiuj plik temlate_new.md do 737.md
```
cp template_new.md 737.md
```
I zmień go według wzoru
```
# Boeing - 737 MAX 8
+ Ilość pasażerów: 210
+ Zasięg: 6570
+ Długość: 39
+ Silniki: 2
```
Dodaj plik i zrób commit
```
git add .
git commit -m "Dodano 737.md"
```
Wypchnij do github
```
git push --set-upstream origin boeing
```
Zmerguj branch boeing do main
```
git checkout main
git merge boeing
```
Wypchnij do github
```
git push
```


## Dane do ćwiczeń

### Boeing

| Model     | Pasażerowie | Zasięg (km) | Długość (m) | Silniki |
|-----------|-------------|-------------|-------------|---------|
| 737 MAX 8 | 210         | 6 570       | 39,5        | 2       |
| 777-300ER | 451         | 13 650      | 73,9        | 2       |
| 787-9     | 296         | 14 010      | 63,0        | 2       |
| 747-8     | 467         | 13 450      | 76,3        | 4       |
| 767-300ER | 269         | 11 070      | 54,9        | 2       |

### Airbus

| Model     | Pasażerowie | Zasięg (km) | Długość (m) | Silniki |
|-----------|-------------|-------------|-------------|---------|
| A320neo   | 186     | 6 300       | 37,6        | 2       |
| A321neo   | 230     | 7 400       | 44,5        | 2       |
| A330-200  | 250     | 13 450      | 58,8        | 2       |
| A350-900  | 350     | 15 000      | 66,8        | 2       |
| A380-800  | 853     | 15 200      | 72,7        | 4       |

### Embraer

| Model  | Pasażerowie | Zasięg (km) | Długość (m) | Silniki |
|--------|-------------|-------------|-------------|---------|
| E170   | 78       | 3 982       | 29,9        | 2       |
| E175   | 88       | 4 074       | 31,7        | 2       |
| E190   | 114      | 4 537       | 36,2        | 2       |
| E195   | 124      | 4 260       | 38,7        | 2       |
| E195-E2| 146      | 4 815       | 41,5        | 2       |

### Bombardier (CRJ Series)

| Model   | Pasażerowie | Zasięg (km) | Długość (m) | Silniki |
|---------|-------------|-------------|-------------|---------|
| CRJ700  | 78          | 2 600       | 32,3        | 2       |
| CRJ900  | 90          | 2 900       | 36,2        | 2       |
| CRJ1000 | 104         | 3 000       | 39,1        | 2       |
| CRJ200  | 50          | 3 148       | 26,8        | 2       |
| CRJ550  | 50          | 1 852       | 32,3        | 2       |

### ATR (turbopropy)

| Model     | Pasażerowie | Zasięg (km) | Długość (m) | Silniki |
|-----------|-------------|-------------|-------------|---------|
| ATR 42-600| 42–50       | 1 560       | 22,7        | 2       |
| ATR 72-600| 68–78       | 1 528       | 27,2        | 2       |