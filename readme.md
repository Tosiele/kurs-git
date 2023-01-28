# Notatki kurs git
## Komendy
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
    - musi mieć opis
    - -a --> wszystkie ziamy zostaną zacommitowane
- git diff
    - pliki nie zacommitowane
    - zmiany po ostatnim commicie
---
## Lokalne + zdalne repozytorium
- git remote add origin [*link do repozytorium utworzonego zdalnie*]
    - pokazanie lokalnemu repo gdzie jest repo zdalne z któym ma się połączyć
- git push origin master
    - przekazuje wszystkie zmiany i commity z lokalnego repo do originu (na branchu master)
- git pull origin master
    - przekazuje wszystkie zmiany i commity z originu do lokalnego repo (na branchu master)
- git clone [*link do repozytorium utworzonego zdalnie*]
    - przed tą komendą należy ustwić się w folderze w którym chcemy zapisać repo
    - pobiera repo utworzone zdalnie razem ze zmianami i commitami
    -tworzy nowe repo lokalne połączone ze zdalnym
---
## Historia commitów
- git log --oneline
    - historia commitów
    - zależność między commitami w repo lokalnym i zdalnym (jak bardzo są zupdatowane)
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
---
## Branche
### Tworzenie
- git branch [*nazwa brancha*]
    - dodajemy nowy branch, ale nie zaczynamy na nim pracować
- git branch
    - wypisuje wszystkie branche i zaznacza ten na którym się znajdujemy
- git checkout -b [*nazwa brancha*]
    - dodajemy nowy branch i zaczynamy w nim pracować
- git branch -d [*nazwa brancha*]
    - usuwa niepotrzebnego brancha
    - warto użyć po zmergowaniu
### Mergowanie
- scala zmiany z różnych branchy
- git merge [nazwa brancha]
    - należy najpierw przenieść się na brancha do któego chcemy coś zmergować
