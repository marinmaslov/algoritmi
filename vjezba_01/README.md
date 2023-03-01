#### [Algoritmi](../) / [Vježba 1](vjezba_01/README.md)

# Vježba 1

## Uvod

Vježba 1 je uvodna vježba u problematiku određivanja složenosti algoritama i bavi se pronalaskom asimptotskih granica (rješavanja suma), odnosno, definiranjem rješenja sume te problematikom dokaza izraza indukcijom.

Prije nego se krene sa rješavanjem zadataka, poželjno je prethodno obrazložiti nekoliko temeljnih informacija. Naime, kasnije vježbe će pokazati da se algoritmi a posebice, petlje, matematički prikazuju pomoću izraza sume (Σ) sa donjom i gornjom granicom (petlja ide od donje do gornje granice). U skripti koja je dostupna na portalu kolegija, u poglavlju 2.4. Sumacije, navedeni su različiti standardni oblici suma i pripadnih rješenja (aritmetički red, geometrijski red, harmonijski red i kvadratni red). Bitno je uočiti da izrazi za sume (na lijevoj strani jednakosti) ima izraz unutar sume te donje i gornje granice a, sa desne strane, kao rješenje sume, jest izraz koji je funkcija f(n). U analogiji, vrijednost n je npr. broj elemenata 1D niza koje je potrebno ispisati sa petljom koja tada mora imati n iteracija. Potrebno vrijeme da algoritam iz navedenog primjera ispiše sve elemente je direktno zavisno o broju elemenata tog niza, odnosno, upravo o parametru n. Rješenje sume je izraz koji nam govori o složenosti algoritma. Navedene sume su standardne i njihova rješenja su poznata. Kako postupiti kada imamo specifičan algoritam koji ima specifičan oblik sume? Odnosno, kako naći rješenje drugih specifičnih oblika suma u ne-standardnim situacijama? U ovoj problematici nam u korist idu upravo pristupi Upotreba grubih granica i Aproksimiranje korištenjem integrala. Navedeni pristupi nam omogućavaju da za dobiveni izraz sume pronađemo pripadno rješenje. Upravo ovom problematikom bavi se 1. zadatak vježbe. Sljedeća problematika vježbe je dokaz indukcijom. Naime, u 2.,3. i 4. zadatku vidljivo je da su zadane sume ali i njihova rješenja. Kako provjeriti da li vrijedi tvrdnja da lijeva strana (izraz sa sumom) je jednak desnoj strani (izraz sa parametrom n)? Dokaz indukcijom nam upravo omogućava da kroz nekoliko koraka i hipoteza provjerimo da li vrijedi tvrdnja da je desna strana odnosno funkcija f(n) (izraz sa parametrom n) rješenje sume koja je na lijevoj strani jednakosti.

## 1. zadatak

Pronađite asimptotske granice (riješite sumu) za slijedeći niz (pretpostavite da je $r>=0$ konstanta):

$$\sum_{i=1}^n i^r$$

## 2. zadatak

Dokažite indukcijom da je slijedeći izraz točan:

$$\sum_{i=1}^n i(i-1)(i-1) = \frac{(n+1)n(n-1)(n-1)}{4}$$

## 3. zadatak

Pokažite indukcijom da li je slijedeći izraz točan:

$$\sum_{i=1}^n (2i-1)^3 = n^2(2n^2-1)$$

## 4. zadatak
Pokažite indukcijom da li je slijedeći izraz točan:

$$\sum_{i=1}^n i(i!) = (n+1)!$$
