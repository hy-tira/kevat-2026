---
title: Tekoälyn käyttöä Tirassa (osa 2)
permalink: /tekoaly2/
hide: true
---

# Tekoälyn käyttöä Tirassa (osa 2)

Yksi kurssin vaikeimmista tehtävistä on viikon 11 tehtävä [Laatikon valinta](https://cses.fi/tira26k/task/3531), jossa on havaittavissa kiinnostava ilmiö: moni opiskelija on ratkaissut tehtävän lähes samalla tavalla suunnilleen seuraavasti:

```python
import bisect

def find_boxes(boxes, products):
    boxes_sorted = sorted(boxes)
    n = len(boxes_sorted)

    parent = list(range(n + 1))

    def find(i):
        if parent[i] != i:
            parent[i] = find(parent[i])
        return parent[i]

    result = []

    for size in products:
        idx = bisect.bisect_left(boxes_sorted, size)
        free_idx = find(idx)

        if free_idx == n:
            result.append(-1)
        else:
            result.append(boxes_sorted[free_idx])
            parent[free_idx] = find(free_idx + 1)

    return result
```

Tällainen ratkaisu pistää silmään, koska käytetty ratkaisutapa on poikkeuksellinen ja usealla opiskelijalla on samanlainen ratkaisu. Ei vaikuta uskottavalta, että opiskelijat olisivat päätyneet samanlaiseen ratkaisuun itsenäisesti.

Kun tehtävänannon antaa tekoälylle, tuloksena on myös samanlainen ratkaisu. Vaikuttaa siltä, että opiskelijat ovat ratkaisseet tehtävän tekoälyllä ja tekoäly tuottaa usein samanlaisen tavallisesta poikkeavan ratkaisun tehtävään.

Tilanne on kuitenkin jotenkin yllättävä, koska tällaisen ratkaisun lähettäneet opiskelijat ovat ratkoneet paljon kurssin tehtäviä, menestyneet hyvin kurssin tentissä ja saamassa kurssin suorituksen korkealla arvosanalla. Mistä tässä on kyse?

<center>***</center>

Kurssin vastuuhenkilö ei ole nähnyt aiemmin tällaista ratkaisua tehtävään, ja tehtävän malliratkaisu on varsin erilainen. Onkin kiinnostavaa miettiä ensin, miten tämä tekoälyratkaisu toimii.

Tehtävässä on tarkoituksena pakata tuotteita laatikoihin niin, että tuotteet käydään läpi tietyssä järjestyksessä ja jokaiselle tuotteelle valitaan pienin laatikko, johon tuote mahtuu. Haasteena on, että kun tuote on pakattu laatikkoon, samaa laatikkoa ei voi käyttää uudestaan toiselle tuotteelle.

Ratkaisu perustuu kahteen ainekseen: binäärihakuun sekä union-find-rakenteeseen. Binäärihaku (`bisect_left`) etsii laatikoiden listasta pienimmän laatikon, johon tuote voidaan pakata. Tässä oletuksena on, että laatikot on järjestetty pienimmästä suurimpaan listalla. Union-find-rakenteen avulla puolestaan selviää tehokkaasti, mikä on seuraava vapaa laatikko tietyn laatikon oikealla puolella.

<center>***</center>

Kurssin vastuuhenkilö otti yhteyttä ratkaisun lähettäneisiin opiskelijoihin ja ehdotti keskustelua asian selvittämiseksi. Kokemus on osoittanut, että yleensä tässä tilanteessa opiskelija ei halua keskustella asiasta ollenkaan tai kieltää käyttäneensä tekoälyä kurssilla millään tavalla. Tällä kertaa keskustelu yhden opiskelijan kanssa oli kuitenkin toisenlainen.

Opiskelija kertoi, että hän tavoitteli kurssista korkeaa arvosanaa ja oli päätynyt ratkaisemaan suuren osan tehtävistä tekoälyllä ajan puutteen takia. Opiskelija kertoi vieneensä tekoälyn käytön niin pitkälle, että hän oli antanut tekoälylle linkin kurssin tehtäväsivustolle, minkä jälkeen tekoäly oli automaattisesti hakenut tehtävät ja tuottanut kaikkien tehtävien ratkaisut.

Tässä on kiinnostavaa, että vaikka opiskelija kertoi ratkaisseensa suuren osan tehtävistä tekoälyllä, kurssin vastuuhenkilö ei pysty näkemään useimmissa opiskelijan ratkaisuissa mitään erityistä tekoälyyn viittaavaa. Jos yksittäisen tehtävän ratkaisu ei olisi kiinnittänyt huomiota, opiskelijaa ei olisi epäilty tekoälyn käytöstä.

Lisäksi on kiinnostavaa, että opiskelija menestyi kurssin tentissä hyvin tekoälyn käytöstä huolimatta. Tämän perusteella kurssin tentti ei ainakaan nykyisellään estä kurssin suorittamista tekoälyllä korkealla arvosanalla.

<center>***</center>

Miksi opiskelijat eivät yleensä tunnusta mitään, vaikka näyttäisi hyvinkin selvältä, että tehtävät on ratkottu tekoälyllä?

Opiskelijan näkökulmasta tekoälyn käytön kieltäminen voi olla järkevää oikeastaan riippumatta siitä, onko käyttänyt tekoälyä vai ei. Vaikka opiskelija olisi käyttänyt tekoälyä, opettajalla ei ole usein loppujen lopuksi riittävää näyttöä asiasta. Jos tekoälyn käytön tunnustaa, kurssin suorituksen menettää varmasti, mutta jos käyttöä ei tunnusta, on ainakin jokin mahdollisuus selviytyä.

Tilanne on erilainen opettajan ja opiskelijan kannalta. Jos vilpillinen opiskelija saa kurssin suorituksen, tämä ei vaikuta opettajan elämään lähes mitenkään. Jos syytön opiskelija tuomitaan tekoälyn käyttäjäksi, tällä voi olla vakavat seuraukset opiskelijan elämään. Tämän takia on vaikea päätös hylätä kurssin suoritus tilanteessa, jossa opiskelija vakuuttaa, ettei ole menetellyt väärin.

Ihannetilanne olisi, ettei olisi ylipäänsä tarvetta yrittää jälkeenpäin selvittää, onko opiskelija ratkonut tehtäviä tekoälyllä.
