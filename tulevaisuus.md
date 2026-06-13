---
title: Tiran tulevaisuus
permalink: /tulevaisuus/
hide: true
---

# Tiran tulevaisuus

Tiran historia ulottuu 1960-luvun loppuun, jolloin Helsingin yliopiston tietojenkäsittelyopin laitos aloitti toimintansa. Alkuvuosina kurssi tunnettiin nimellä _Informaatiostruktuurit_ ja myöhemmin nimellä _Tietorakenteet_, joka laajeni lopulta muotoon _Tietorakenteet ja algoritmit_. Jyrki Kivisen arkistosta löytynyt [kurssikuvaus vuodelta 1975](../informaatiostruktuurit.pdf) antaa näytteen siitä, millainen kurssi oli ennen.

Tärkeä muutos Tiran historiassa on, että kurssin painopiste on siirtynyt tietorakenteiden toteuttamisesta algoritmien suunnitteluun. Ohjelmoijalle oli aiemmin tärkeämpää tuntea yksityiskohtaisesti tietorakenteiden toteutustapoja, koska ohjelmointikielissä oli niukasti valmiita tietorakenteita. Nykyään tilanne on toinen, koska modernit ohjelmointikielet tarjoavat kattavan valikoiman valmiita tietorakenteita. Esimerkiksi Pythonissa ohjelmoijan ei tarvitse toteuttaa itse hajautustaulua, koska tarjolla ovat valmiit `dict`- ja `set`-tietorakenteet.

Seuraavassa on mietteitä Tiran nykytilanteesta ja ideoita kurssin kehittämiseen.

<center>***</center>

Tiran opettamiseen on tuonut tiettyä haastetta, että kurssin opetuskieli on Python, joka on korkean tason ohjelmointikieli. Vaikka Python soveltuu hyvin ohjelmoinnin opettamiseen, tietorakenteiden toteuttamisessa olisi usein mielekästä käyttää matalan tason kieltä kuten C-kieltä.

Ensi syksynä alkavalla matalan tason ohjelmointikurssilla (valinnainen kandikurssi) toteutetaan C-kielellä perustietorakenteita, kuten taulukkolista, linkitetty lista ja hajautustaulu. Tämän takia Tirassa painotusta voisi siirtää jopa nykyistä enemmän korkeammalle tasolle. Toisaalta yleissivistyksen takia Tirassa on hyvä käsitellä jollain tavalla myös matalan tason tietorakenteita.

Linkitetty lista esiintyy tällä hetkellä ohimennen vasta kurssin II-osassa, ja voisi olla mielekästä käsitellä sitä I-osassa listojen yhteydessä.

<center>***</center>

Tällä hetkellä Tirassa ei tule esille tietorakenteiden ja algoritmien historiaa. Kurssilla voisi kertoa, miten ja milloin asiat ovat syntyneet ja miten tietokoneiden ja ohjelmointikielten kehitys on vaikuttanut asioihin.

Kurssilla ei käsitellä binäärihakua ja pikajärjestämistä. Nämä molemmat aiheet kuuluvat yleissivistykseen, ja ne olisi hyvä lisätä kurssille.

Kurssin sisältöä ja tehtäviä voisi olla hyvä viedä teoreettisempaan suuntaan ja käsitellä paremmin $$O$$-notaatiota ja algoritmeihin liittyviä todistuksia. Tässä on kuitenkin haasteena, että monilla kurssin osallistujilla on vain vähän matemaattista taustaa, minkä takia teoria-aiheiden opettaminen on vaikeaa.

<center>***</center>

Nykyinen tapa käsitellä dynaamista ohjelmointia Tirassa tuntuu liian vaikealta. Ehkä hyvä ratkaisu olisi keskittyä analysoimaan olemassa olevia dynaamisen ohjelmoinnin algoritmeja eikä edellyttää algoritmien suunnittelemista itse. Ajatus koodin tehostamisesta tallentamalla välituloksia muistiin sopii kuitenkin hyvin Tiraan.

Maksimivirtausta käsitellään kattavasti myös maisteritasolla, mutta toisaalta aihe on tuntunut sopivan hyvin myös Tiraan.

<center>***</center>

Mikä on Tiran merkitys tekoälyn aikakautena? Vaikka ohjelmoija ei tuntisi Tiran asioita, hän voisi valita sopivat tietorakenteet ja tuottaa tehokasta koodia tekoälyn avulla. Yksi tärkeä syy opiskella Tiraa on kuitenkin siinä, että kurssi kehittää ajattelua ja kykyä ratkaista ongelmia.

Tiran tehtävien ratkomista voi verrata esimerkiksi shakin pelaamiseen. Tekoäly on jo kauan osannut pelata shakkia ihmistä paremmin, mutta tämä ei ole johtanut siihen, ettei kukaan ihminen enää pelaisi shakkia.

Tiran nykyinen toteutustapa ei ehkä tue enää hyvin tavoitetta kehittää opiskelijan ajattelua ja osaamista. Kurssin arviointi perustuu pääosin itsenäisiin tehtäviin, mutta tehtävien ratkaisemisen voi [ulkoistaa helposti tekoälylle](../tekoaly2). Tämän takia voi miettiä, onko kurssin arvioinnissa tulevaisuudessa järkevää ottaa huomioon lainkaan tehtäviä, jotka on ratkaistu ilman valvontaa.

Tulisiko kurssin arviointia muuttaa niin, että arviointi perustuu pelkkään tenttiin? Ehkä, mutta tässä toteutustavassa olisi kaksi haastetta. Ensinnäkin motivaatio ratkaista kurssitehtäviä voisi laskea merkittävästi, jos tehtävät eivät vaikuttaisi kurssin arviointiin. Lisäksi tenttitilanteessa on vaikeaa mitata sitä, osaako opiskelija ratkaista vaikeita algoritmien suunnittelun tehtäviä.
