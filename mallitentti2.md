---
title: Mallitentti (II-osa)
permalink: /mallitentti2/
hide: true
---

# Mallitentti (II-osa)

Seuraava mallitentti antaa näytteen siitä, millainen on kurssin II-osan tentti.

Tentti muodostuu viidestä tehtävästä, jotka ovat samantapaisia kuin mallitentissä. Kurssin suoritus vaatii, että ratkaiset ainakin neljä ensimmäistä tehtävää. Arvosana 5 vaatii, että ratkaiset myös viimeisen tehtävän.

## Tehtävä 1

Tehtävä 1 on ohjelmointitehtävä, jonka aiheena on ohjelmoinnin perusteet. Sinun tulee ratkaista tämä tehtävä, jotta pääset kurssin läpi.

**Esimerkkitehtävä**

Tee Python-funktio `create_list(n)`, joka palauttaa listan, jossa on kerran luku 1, kahdesti luku 2, kolmesti luku 3, jne. lukuun `n` asti.

Esimerkiksi jos `n = 4`, funktion tulee palauttaa lista `[1, 2, 2, 3, 3, 3, 4, 4, 4, 4]`.

**Malliratkaisu**

```python
def create_list(n):
    result = []
    for i in range(1, n + 1):
        for j in range(i):
            result.append(i)
    return result
```

## Tehtävä 2

Tehtävässä 2 sinun tulee kertoa, minkä tuloksen tietty kurssilla käsitelty verkkoalgoritmi tuottaa annetulle verkolle. Sinun tulee ratkaista tämä tehtävä, jotta pääset kurssin läpi.

**Esimerkkitehtävä**

Minkä tuloksen Dijkstran algoritmi antaa seuraavalle verkolle, kun aloitussolmu on solmu 1?

![](../img/lyhpol.png)

**Malliratkaisu**

Dijkstran algoritmi laskee lyhimmän etäisyyden aloitussolmusta kuhunkin solmuun. Tässä tapauksessa algoritmi antaa seuraavat etäisyydet:

- Solmu 1: 0
- Solmu 2: 4
- Solmu 3: 1
- Solmu 4: 3
- Solmu 5: 6

## Tehtävä 3

Tehtävässä 3 sinun tulee antaa esimerkki verkosta, jolla on tiettyjä ominaisuuksia. Sinun tulee ratkaista tämä tehtävä, jotta pääset kurssin läpi.

**Esimerkkitehtävä**

Anna esimerkki verkosta, jossa on viisi solmua ja kolme vahvasti yhtenäistä komponenttia. Ilmoita jokaisesta komponentista, mitkä solmut kuuluvat siihen.

**Malliratkaisu**

Tässä on halutunlainen verkko:

![](../img/suuver.png)

Vahvasti yhtenäiset komponentit ovat $$\{1,2,4\}$$, $$\{3\}$$ ja $$\{5\}$$.

## Tehtävä 4

Tehtävässä 4 sinun tulee näyttää, miksi annettu ahne algoritmi ei ole toimiva. Sinun tulee ratkaista tämä tehtävä, jotta pääset kurssin läpi.

**Esimerkkitehtävä**

Tehtävänä on muodostaa listan pisin nouseva alijono eli kerätä listalta mahdollisimman monta alkiota vasemmalta oikealle kulkien niin, että jokainen alkio on edellistä suurempi.

Ahne algoritmi: valitaan ensin listan pienin alkio, sitten pienin edellistä suurempi alkio tämän oikealla puolella, jne. Esimerkiksi listassa $$[5,1,3,2,4]$$ algoritmi valitsee ensin alkion $$1$$, sitten alkion $$2$$ ja lopuksi alkion $$4$$, jolloin tulee pisin nouseva alijono $$[1,2,4]$$.

Näytä esimerkki listasta, jossa tämä ahne algoritmi ei toimi oikein. Minkä tuloksen algoritmi antaa ja miksi se on väärin?

**Malliratkaisu**

Ahne algoritmi ei toimi oikein esimerkiksi listassa $$[2,3,1]$$. Tässä listassa algoritmi muodostaa alijonon $$[1]$$ mutta pisin nouseva alijono on $$[2,3]$$.

## Tehtävä 5

Tehtävä 5 on vaikeampi teoreettinen tehtävä. Sinun tulee ratkaista tämä tehtävä, jos haluat kurssista arvosanan 5. Tehtävä ei vaikuta muihin arvosanoihin.

**Esimerkkitehtävä**

Verkon jokaisella kaarella on eri paino. Todista, että pienimmässä virittävässä puussa on varmasti kaari, jonka paino on pienin.

**Malliratkaisu**

Oletetaan, että painoltaan pienin kaari $$e$$ on solmujen $$x$$ ja $$y$$ välillä.

Oletetaan, että on muodostettu virittävä puu, jossa ei ole kaarta $$e$$. Tässä puussa täytyy olla jokin polku solmusta $$x$$ solmuun $$y$$. Kun jokin tämän polun kaarista korvataan kaarella $$e$$, saadaan toinen virittävä puu, jonka paino on aiempaa pienempi. Niinpä alkuperäinen virittävä puu ei ollut pienin virittävä puu ja väite on todistettu.
