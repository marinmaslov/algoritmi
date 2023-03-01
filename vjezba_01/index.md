#### 🧭 [Algoritmi](../) / [Vježba 1](vjezba_01/README.md)

# Vježba 1 📒

## Sadržaj ℹ️
  * [Uvod](#uvod-)
  * [1. zadatak](#1-zadatak-)
    + [(i) Upotreba grube granice](#i-upotreba-grube-granice-)
    + [(ii) Aproksimacija korištenjem integrala](#ii-aproksimacija-korištenjem-integrala-)
  * [2. zadatak](#2-zadatak-)
  * [3. zadatak](#3-zadatak-)
  * [4. zadatak](#4-zadatak-)

## Uvod 📢

Ovo je uvodna vježba u problematiku određivanja složenosti algoritama i bavi se pronalaskom asimptotskih granica (rješavanja suma), odnosno, definiranjem rješenja sume te problematikom dokaza izraza indukcijom. Dakle, rješenje zapravo predstavlja složenost.

Svi algoritmi, posebice petlje, matematički se mogu prikazati pomoću izraza sume $Σ$ s donjom i gornjom granicom, gdje petlja kreće od donje te ide prema gornjoj granici).

U skripti koja je dostupna na portalu kolegija, u poglavlju 2.4. Sumacije, navedeni su različiti standardni oblici suma i pripadnih rješenja (aritmetički red, geometrijski red, harmonijski red i kvadratni red). Bitno je uočiti da izrazi za sume (na lijevoj strani jednakosti) ima izraz unutar sume te donje i gornje granice a, sa desne strane, kao rješenje sume, jest izraz koji je funkcija f(n).

U analogiji, vrijednost n je npr. broj elemenata 1D niza koje je potrebno ispisati sa petljom koja tada mora imati n iteracija. Potrebno vrijeme da algoritam iz navedenog primjera ispiše sve elemente je direktno zavisno o broju elemenata tog niza, odnosno, upravo o parametru n. Rješenje sume je izraz koji nam govori o složenosti algoritma. Navedene sume su standardne i njihova rješenja su poznata. Kako postupiti kada imamo specifičan algoritam koji ima specifičan oblik sume? Odnosno, kako naći rješenje drugih specifičnih oblika suma u ne-standardnim situacijama? U ovoj problematici nam u korist idu upravo pristupi: Upotreba grubih granica i Aproksimiranje korištenjem integrala.

Navedeni pristupi nam omogućavaju da za dobiveni izraz sume pronađemo pripadno rješenje. Upravo ovom problematikom bavi se 1. zadatak vježbe. Sljedeća problematika vježbe je dokaz indukcijom. Naime, u 2.,3. i 4. zadatku vidljivo je da su zadane sume ali i njihova rješenja. Kako provjeriti da li vrijedi tvrdnja da lijeva strana (izraz sa sumom) je jednak desnoj strani (izraz sa parametrom n)? Dokaz indukcijom nam upravo omogućava da kroz nekoliko koraka i hipoteza provjerimo da li vrijedi tvrdnja da je desna strana odnosno funkcija f(n) (izraz sa parametrom n) rješenje sume koja je na lijevoj strani jednakosti.

### Označavanje složenosti
Postoji nekoliko načina označavanja složenosti, na ovom kolegiju ćemo se uglavnom držati $\Theta$ notacije, međutim upoznat ćete se i s [drugim tipovima označavanja](https://www.geeksforgeeks.org/difference-between-big-oh-big-omega-and-big-theta/).


UZET BOLJI PRIMJER S NETA.! --> DOBAR JE I OVAJ

### Određivanje složenosti

Primjerice, recimo da imamo napisan program koji zbraja sve potencije broja 2 u rasponu od 0 do 6:
``` python
sum = 0

for i in range(0, 7):
    sum = sum + pow(2, i)

print("Suma je: ", sum)
```

gdje, kada pokrenemo kod, dobijemo sljedeći ispis:
``` bash
Suma je:  127
```

Matematički zapis ovog našeg "algoritma" je:

$$\sum_0^{7} 2^i = 1 + 2 + 4 + 8 + 16 + 32 + 64 = 127$$

Poznate su nam donja (0) i gornja (6) granica pa je vremenska kompleksnost ovdje $\Theta(1)$, no promijenimo to... Recimo da želimo proširiti program tako da zbraja sve potencije broja 2 do neke potencije $n$ koju će korisnik unijeti (ali je mi ne znamo).

Izraz nam sada poprima sljedeći oblik:
$$\sum_0^{n} 2^i$$

Koliko je kompleksnost ovog našeg novog algoritma?

Kao što je već i navedeno, postoje dva pristupa kod određivanja kompleksnosti tj. rješavanju sume:

#### (i) Upotreba grubih granica

#### (ii) Aproksimiranje korištenjem integrala


--------------




____________________________

## 1. zadatak 🚀

Pronađite asimptotske granice (riješite sumu) za slijedeći niz (pretpostavite da je $r>=0$ konstanta):

$$\sum_{i=1}^n i^r$$

____________________________

Pronaći asimptotske granice znači riješiti sumu! Preporuka je proučiti 12. stranicu [skripte](https://moodle.srce.hr/2022-2023/mod/resource/view.php?id=3124577) iz algoritama!

Zadano je: $$\sum_{i=1}^n i^r$$

<b>Za ovakav tip zadatka postoje 2 pristupa:</b>
____________________________

### (i) Upotreba grube granice 🔝

Zamijenimo $i$ iz izraza s gornjom granicom $n$:

$$\sum_{i=1}^n i^r = \sum_{i=1}^n n^r$$

Također, zamijenimo i izraz za sumu s gornjom granicom $n$:

$$\sum_{i=1}^n n^r = n⋅n^r$$

Nakon sređivanja dobijemo:

$$\sum_{i=1}^n n^r = n⋅n^r = n^{r+1}$$

Kompleksnost: $$\Theta(n^{r+1})$$ DODAT DETALJE O KOMPLEKSNOSTI!
____________________________

### (ii) Aproksimacija korištenjem integrala 🧮

Ako pogledamo skriptu, možemo zaključiti da vrijedi sljedeće:

$$\int_0^n f(x)dx \leq \sum_{i=1}^n f(i) \leq \int_1^{n+1} f(x)dx$$

Uvrstimo našu funkciju u desnu stranu izraza:

$$\sum_{i=1}^n i^r \leq \int_1^{n+1} i^rd(i)$$

Sada riješimo integral:

$$\sum_{i=1}^n i^r \leq \int_1^{n+1} i^rd(i) = \frac{i^{r+1}}{r+1}\Biggr|_{i=1}^{i=n+1} = \frac{(n+1)^{r+1}}{r+1} - \frac{1^{r+1}}{r+1}$$

Ovdje valja primijetiti sljedeće:
- $r$ je konstanta, pa su i izrazi $r+$ i $r^{r+1}$ konstante
- kako su navedeni izrazi konstante rješnje isključivo ovisi o izrazu $(n+1)^{r+1}$

Kako rješenje isključivo ovisi $(n+1)^{r+1}$, razmotrimo ga.

Raspisivanjem [binomnog poučka](https://hr.wikipedia.org/wiki/Binomni_poučak) dobije se izraz s različitim koeficijentima u kojem je ponovo vidljivo da je samo jedan dominantan, a to je $n^{r+1}$.

Prema tome vrijedi:

$$\frac{(n+1)^{r+1}}{r+1} - \frac{1^{r+1}}{r+1} \approx n^{r+1}$$

Kompleksnost: $$\Theta(n^{r+1})$$ DODAT DETALJE O KOMPLEKSNOSTI!
____________________________

Oba pristupa, $(i)$ i $(ii)$ moraju imat isto rješenje.




____________________________

## 2. zadatak 🍭

Dokažite indukcijom da je slijedeći izraz točan:

$$\sum_{i=1}^n i(i-1)(i-1) = \frac{(n+1)n(n-1)(n-1)}{4}$$

## 3. zadatak 🔥

Pokažite indukcijom da li je slijedeći izraz točan:

$$\sum_{i=1}^n (2i-1)^3 = n^2(2n^2-1)$$

## 4. zadatak 🪐
Pokažite indukcijom da li je slijedeći izraz točan:

$$\sum_{i=1}^n i(i!) = (n+1)!$$
