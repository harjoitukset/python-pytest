# Yksikkötestaus Pytest-työkalulla

Näissä tehtävissä harjoittelemme koodin refaktorointia ja yksikkötestausta kirjoittamalla testejä aikaisemmin koodatulle `02_postinumerot.py`-skriptille (edellisen viikon tehtävän 2. osa).

Mikäli aikaisempi tehtävä jäi sinulta palauttamatta tai et halua käyttää vanhaa koodiasi, voit käyttää myös tehtävän malliratkaisun tiedostoja, jotka löydät Teams-kanavalta tehtävän umpeutumisen jälkeen.

Pytest-työkalun asennus onnistuu esimerkiksi seuraavasti:

```
$ pip3 install pytest
```

Tehtävät arvostellaan käyttäen [GitHub classroom](https://classroom.github.com/) -palvelua, joka suorittaa komentosi, ja tarkastaa ja pisteyttää niiden tulokset automaattisesti. Taustalla GitHub classroom hyödyntää [GitHub actions](https://github.com/features/actions) -nimistä jatkuvan integroinnin palvelua. Voit tarvittaessa yrittää tehtäviä monta kertaa. Tee tällöin uusi commit, ja vie muutokset uudelleen GitHubiin.


## Harjoitusten kloonaaminen

Kun olet hyväksynyt tehtävän GitHub classroomissa ja saanut repositoriosta henkilökohtaisen kopion, kloonaa se itsellesi `git clone` -komennolla.

Kloonatessasi repositoriota varmista, että Git-osoitteen lopussa on oma GitHub-käyttäjänimesi. Jos käyttäjänimesi puuttuu osoitteesta, kyseessä ei ole henkilökohtainen kopiosi tehtävästä. Luo tässä tapauksessa oma repositorio tämän linkin kautta: TODO.


## Osa 1: Postinumeroiden etsimisen testit (3 pistettä)

Luo repositorioosi uusi tiedosto, johon kirjoitat Pytest-yksikkötestit edellisen viikon Python-tehtävän osan 2 ratkaisullesi, eli `02_postinumerot.py` skriptille. Mikäli kyseinen tehtävä jäi sinulta toteuttamatta, voit käyttää testattavana koodina tehtävän malliratkaisua.

Sinun ei tarvitse testata koko ohjelmalogiikkaa, vaan riittää, että testaat esimerkiksi yksittäisen funktion. Lisäksi joudut refaktoroimaan Python-tiedostoa siten, että sen testaaminen on ylipäänsä mahdollista.

Testeissä varmista ainakin seuraavien tapausten toiminta:

1. postitoimipaikan nimellä löytyy vain yksi postinumero
1. postitoimipaikan nimellä löytyy useita postinumeroita
1. postitoimipaikan nimellä ei löydy lainkaan postinumeroita.

Testien suorittaminen onnistuu seuraavalla komennolla:

```
$ python3 -m pytest
```

Muista lisätä testitiedostosi versionhallintaan `git add`- ja `git commit`-komennoilla.

Saadaksesi täydet pisteet tästä osasta **sinun ei tarvitse** testata syötteitä pyytäviä tai tulosteita tekeviä kohtia koodista. Voit oman harkintasi mukaan käyttää testeissä joko kovakoodattua testidataa tai antaa testattavan koodin lukea postinumeroaineiston verkosta tai levyltä. Testiaineiston käyttämisessä `pytest-mock` voi olla avuksi, mutta sitä **ei ole välttämätöntä käyttää**.



## Osa 2: Bugin korjaus ja testaus (2 pistettä)

Postin aineistossa smart post -automaatit esiintyvät sekä nimellä "smart post" että "smartpost". Ohjelmasi toimintaa tulee muuttaa siten, että se löytää kaikki smart post -automaatit riippumatta siitä, esiintyykö niiden nimessä välilyöntiä tai välimerkkejä. Kirjoita myös yksikkötestit, jotka osoittavat tekemäsi muutoksen toimivan.

Ohjelman käyttöliittymän tulee toimia samalla tavoin, kuin [edellisessä tehtävässä](https://github.com/harjoitukset/python-postalcodes).

Bugin korjauksessa voi olla avuksi, jos poistat kaikki välilyönnit [Pythonin replace-funktiolla](https://stackoverflow.com/questions/9452108/how-to-use-string-replace-in-python-3-x).

Esimerkkisuoritus:

```
$ python3 02_postinumerot.py 
Kirjoita postitoimipaikka: smart post
Postinumerot: 00104, 00124, 00134, 00144, ..., 40934, ... 99304, 99604, 99804, 99834, 99874, 99944, 99954, 99994
```

Yllä 40934 löytyy aineistosta nimellä "SMART POST", kun muut löytyvät nimellä "SMARTPOST".
