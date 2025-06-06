# Notatki kurs git

## Ogólne komendy
- git innit
    - inicjalizuje nowe repozytorium w wybranym folderze
- git add [*nazwa pliku, --all*] 
    -  zaczyna śliedzić nowy plik (wszyskie pliki)--> dodaje go do repozytorium
    - odwrotność to git rm (remove)
- git status 
    - pliki nie śledzone
    - pliki nie zacommitowane
    - zmiany lokalne
- git commit [*pliki do zacommitowania*]
    - zatwierdza i zapisuje w historii zmiany
    - musi mieć nazwę/message --> konkretny żeby łatwo było odnaleźć zmiany, jednolity z pozostałymi opisami
    - -a --> wszystkie ziamy zostaną zacommitowane
    - -m [*message commita*] -m [*opcjonalny dokładniejszy opis wprowadzonych zmian*]
- git diff
    - pliki nie zacommitowane
    - zmiany po ostatnim commicie

---

## Lokalne + zdalne repozytorium
- git remote add origin [*link do repozytorium utworzonego zdalnie*]
    - pokazanie lokalnemu repo gdzie jest repo zdalne z któym ma się połączyć
- git push origin master
    - przekazuje wszystkie zmiany i commity z lokalnego repo do originu (na branchu master - branchu który chcemy wypchnąć)
- git pull origin master
    - przekazuje wszystkie zmiany i commity z originu do lokalnego repo (na branchu master - branchu który chcemy zaciągnąć)
    - fetch + merge
- git clone [*link do repozytorium utworzonego zdalnie*]
    - przed tą komendą należy ustwić się w folderze w którym chcemy zapisać repo
    - pobiera repo utworzone zdalnie razem ze zmianami i commitami
    - tworzy nowe repo lokalne połączone ze zdalnym
    - **(albo odwrotnie)**
- git fetch
    - pobiera zmiany z repozytorium zdlanego ale nie ingeruje w repozytorium lokalne

---

## Historia commitów
- git log --oneline
    - historia commitów
    - zależność między commitami w repo lokalnym i zdalnym (jak bardzo są zupdatowane)
    - -S [*ciąg znaków znajdujący się w commicie*] --> pozwala przeszukać historię na podstawie wpisanego ciągu znaków jaki myślimy że znajduje się w szukanym przez ans commicie
        - -p --> pokazuje zmiany bardziej szczegółowo
- gitk
    - pokazuje historię w ładny graficznie sposób w osobnym oknie
    - pokazuje czy mamy jakieś lokalne nie zacommitowane zmiany
    - --all --> pokazuje histroię wszystkiego a nie tylko naszego brancha
- git checkout
    - cofa repo w czasie do momentu na który go ustawimy
    - umożliwia dokonanie zmian w poprzednich wersjach repo
    - commit [*hash commita*]
        - pokyzkujemy go z git log
    - tag [*nazwa taga*]
        - możemy nazwać dany commit za pomocą git tag [*tag jaki dodajemy*] [*hash commita*]
    - [*nazwa brancha*]
        - pozwala zacząć pracować na danym branchu
    - *-*
        - pozwala cofnąć się w czasie o jednego commita
- git gui blame [*nazwa pliku*]
    - pokazuej **kto** zrbił **które** zmiany w danym pliku
### Modyfikacja historii
- **lokalnie zawsze, zdalnie w ogóle**
- git commit --amend
    - zmiany w ostatnim commicie
- git revert
    - cofa wszystkie zmiany z ostatniego commita (tworzy nowy commit)

---

## Branche
### Tworzenie
- git branch
    - wypisuje wszystkie branche i zaznacza ten na którym się znajdujemy
- git branch [*nazwa brancha*]
    - dodajemy nowy branch, ale nie zaczynamy na nim pracować
- git checkout -b [*nazwa brancha*]
    - dodajemy nowy branch i zaczynamy w nim pracować
- git branch -d [*nazwa brancha*]
    - usuwa niepotrzebnego brancha
    - warto użyć po zmergowaniu
- git chery-pick [*nazwa commita*]
    - pozwala przenosić pojedynczy commit pomiędzy branchami

### Mergowanie
- scala zmiany z różnych branchy
- git merge [nazwa brancha]
    - należy najpierw przenieść się na brancha do którego chcemy coś zmergować
- jeśli historia branchy nie jest wspólna trzeba manualnie rozwiązać konflikt (lub nie - późniejsza część kursu)

---

## Ignorowanie
- w głównym folderze ropozytorium stwórz plik *.gitignore*
- jest to plik tekstowy w którym można wpisać co chcemy żeby było ignorowane i nie śledzone przez gita:
    - [*nazwa pliku - abc.txt*] --> ignoruje konkretny plik
    - [*.rozszerzenie - *.txt] --> ignoruje wszystkie pliki o danego typu
    - [*.nazwa folderu/ - .projekt1/*] --> ignoruje cały folder
---

## Zasady commit message
- *feat* – a new feature is introduced with the changes

- *fix* – a bug fix has occurred

- *chore* – changes that do not relate to a fix or feature and don't modify src or test files (for example updating dependencies)

- *refactor* – refactored code that neither fixes a bug nor adds a feature

- *docs* – updates to documentation such as a the README or other markdown files

- *style* – changes that do not affect the meaning of the code, likely related to code formatting such as white-space, missing semi-colons, and so on.

- *test* – including new or correcting previous tests

- *perf* – performance improvements

- *revert* – reverts a previous commit