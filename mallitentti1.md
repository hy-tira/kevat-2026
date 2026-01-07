---
title: Mallitentti (I-osa)
permalink: /mallitentti1/
hide: true
---

# Mallitentti (I-osa)

Seuraava mallitentti antaa näytteen siitä, millainen on kurssin I-osan tentti.

Tentti muodostuu viidestä tehtävästä, jotka ovat samantapaisia kuin mallitentissä. Kurssin suoritus vaatii, että ratkaiset ainakin neljä ensimmäistä tehtävää. Arvosana 5 vaatii, että ratkaiset myös viimeisen tehtävän.

Ohjelmointitehtävissä koodi tulee toteuttaa Python-kielellä. Oleellista on, että koodin logiikka ja kokonaisuus ovat kunnossa. Erityisesti pieneet virheet (esim. jostain puuttuu sulku) eivät haittaa.

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

Tehtävä 2 sisältää kymmenen monivalintakysymystä liittyen kurssin perusasioihin. Sinun tulee saada vähintään kahdeksan kysymystä oikein, jotta pääset kurssin läpi.

**Esimerkkitehtävä (osa)**

1. Pythonissa listan metodi `index` etsii annetun alkion indeksin listalla. Mikä on metodin aikavaativuus?
  (a) $$O(1)$$
  (b) $$O(\log n)$$
  (c) $$O(n)$$
  (d) $$O(n^2)$$

2. Mitä seuraava Python-koodi tulostaa?
```python
a = [4, 3, 2, 1]
b = sorted(a)
print(a[0])
```
   (a) 1
   (b) 2
   (c) 3
   (d) 4

3. Verkossa on 8 solmua ja 5 kaarta. Montako komponenttia verkossa on vähintään?
   (a) 3 (b) 4 (b) 5 (b) 6

**Malliratkaisu (osa)**

1. Metodin aikavaativuus on $$O(n)$$.
2. Koodi tulostaa luvun 4.
3. Verkossa on vähintään 3 komponenttia.

## Tehtävä 3

Tehtävä 3 on ohjelmointitehtävä, jossa tulee toteuttaa $$O(n)$$-aikainen tehokas algoritmi. Sinun tulee ratkaista tämä tehtävä, jotta pääset kurssin läpi.

Tehtävän ratkaisuun riittää koodi, jossa for-silmukka käy listan läpi ja käsittelee muuttujia sopivalla tavalla.

**Esimerkkitehtävä**

Tee Python-funktio `count_pairs(numbers)`, joka kertoo, monellako tavalla listasta voidaan valita kaksi eri kohdissa olevaa lukua niin, että lukujen summa on parillinen. Funktion aikavaativuuden tulee olla $$O(n)$$.

Esimerkiksi jos lista on `[1, 2, 1, 4]`, haluttu tulos on 2, koska mahdolliset parit ovat (1, 1) ja (2, 4).

**Malliratkaisu**

```python
def count_pairs(numbers):
    even_count = odd_count = 0
    result = 0
    for number in numbers:
        if number % 2 == 0:
            result += even_count
            even_count += 1
        else:
            result += odd_count
            odd_count += 1
    return result
```

## Tehtävä 4

Tehtävä 4 on ohjelmointitehtävä, jossa tulee toteuttaa rekursiivinen algoritmi puun läpikäyntiin. Sinun tulee ratkaista tämä tehtävä, jotta pääset kurssin läpi.

Tehtävän ratkaisuun riittää koodi, joka käy läpi rekursiivisesti solmun lapset ja laskee halutun tuloksen muuttujien avulla.

**Esimerkkitehtävä**

Toteuta rekursiivinen funktio `count_leaves(node)`, joka laskee, montako lehteä annetussa puussa on. Funktiolle annetaan parametrina puun juurisolmu. Puu on esitetty seuraavan luokan avulla:

```python
class Node:
    def __init__(self, value, children=[]):
        self.value = value
        self.children = children

    def __repr__(self):
        return str(self.value)
```

**Malliratkaisu**

```python
def count_leaves(node):
    if node.children == []:
        return 1

    result = 0
    for child in node.children:
        result += count_leaves(child)
    return result
```

## Tehtävä 5

Tehtävä 5 on vaikeampi teoreettinen tehtävä. Sinun tulee ratkaista tämä tehtävä, jos haluat kurssista arvosanan 5. Tehtävä ei vaikuta muihin arvosanoihin.

**Esimerkkitehtävä**

Funktio $$f(n)$$ kuuluu luokkaan $$O(g(n))$$, jos voidaan valita positiiviset vakiot $$c$$ ja $$n_0$$ niin, että $$f(n) \le c g(n)$$, kun $$n \ge n_0$$.

Todista tämän määritelmän perusteella, että $$f(n)=n^2$$ ei kuulu luokkaan $$O(n)$$.

**Malliratkaisu**

Tehdään vastaoletus, että $$f(n)=n^2$$ kuuluu luokkaan $$O(n)$$. Tällöin $$n^2 \le cn$$ jollain vakiolla $$c$$, kun $$n \ge n_0$$. Tämä tarkoittaisi, että $$n \le c$$, mikä ei ole kuitenkaan mahdollista, koska $$n$$ voi kasvaa rajatta ja $$c$$ on vakio. Vastaoletus ei päde ja väite on todistettu.
