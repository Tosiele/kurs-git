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
- git commit [-a]
    - zatwierdza i zapisuje w historii zmiany
    - musi mieć opis
    - -a wszystkie ziamy zostaną zacommitowane
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
