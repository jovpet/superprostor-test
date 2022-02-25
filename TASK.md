#TASK

## Overview

Zadatak je da se implementira product overview stranica, koja se sastoji od tri manje komponente: filtera, grida i paginacije. Filter sluzi da bi korisniku omogucio da postavi kriterijum za prikaz podataka. Grid predstavlja vizualizaciju date i omogucava sortiranje. Paginacija sluzi za navigaciju izmedju stranica.

svaka komponenta treba da ima pristup state-u deljenom sa drugim komponentama. Npr. filter treba da resetuje paginaciju na 1 kada se kriterijum promeni, grid treba da zna koji je kriterijum i koja stranica su aktivani kada vrsi refresh.

filteri: drvo, beton ili staklo
sort: id, title

### 1. Kreirati service koji sadrzi informacije:

1. filter (koji filter je primenjen)
2. sort (koji kriterijum sortiranja je primenjen)
3. currentPage
4. totalPages
5. data

### 2. Kreirati Filter komponentu

1. filter komponenta nema atributa
2. filter komponenta se subscribuje na datu iz servisa i prikazuje opcije za setovanje kriterijuma (drvo, staklo ili beton) sa brojem itema u svakom od tri tipa. npr:
*******************
 Drvo (33)
*******************
 Beton (24)
*******************
 Staklo (43)
*******************
3. klik na svaki od kriterijuma resetuje current page na 1, setuje totalPages i filter u servisu

### 3. kreirati grid view komponentu

1. grid komponenta nema atributa
2. grid u zavisnosti od setovanog filtera, prikazuje 5 itema po stranici.
3. kreirati iznad itema switcher za setovanje sortiranja (sortiraj po id / naslovu).Default vrednost je po "id"-u.
4. promena sortiranja resetuje currentPage

### 4. kreirati paginaciju

1. komponenta nema atributa
2. limit je 5 itema po strani
3. komponenta setuje currentPage u servisu

### 5. Ucitavanje date i setovanje stranice

u app componenti prikazati lodaing text dok se json ne ucita. Ucitane json podatke setovati kao data value u servis. 

## NOTES

Dozvoljeno je koriscenje Boostrasp, Material ili bilo kog drugog css frameworka. Bootstrap included by default.
Mock data se nalazi na adresi `localhost:3300/data`. Mock server se pokrece komandom `node server.js`
Struktura date je array koji sadrzi:
{
    id: number;
    title: string;
    type: 'drvo' | 'staklo' | 'beton',
    description: string;
}
