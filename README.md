# palvelint3
Palvelinten hallinta kurssin tehtävä 3.

Tehtävän tekemiseen käytetty virtuaalikonetta:
  * VirtualBox
  * 2 prosessoriydintä
  * 4 GB muistia
  * 20GB levytilaa

Tehtävä kirjoitettu käyttäen MarkDownia ja nano kirjoitusohjelmaa, kuvat löytyvät blogisivulta.
Muotoilua muutettu artikkelin https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet ohjeilla

# Git
Loin tehtävälle uuden repositorion README:lla, ja kloonasin sen virtuaalikoneelle kansioon gitstuff.
Kloonattuun repoon siirryin cd palvelint3, ja lähdin muokkaamaan README.md tiedostoa.

Lisättyäni tekstiä tähän asti, olin tyytyväinen aloitukseen, ja tallensin tiedoston, ja lisäsin sen komennolla `git add` . ja `git commit;`
Tämän jälkeen katsoin mitä komento git log antaa, 
**(kuva1)**

ja tästä voidaan päätellä, että ensimmäinen initial commit tarkoitti kloonausta, tässä original author nimenä on GitHug tilini nimi ja email, milloin tämä on tehty, sekä ylhäällä commit ja pitkä kirjain numeroyhdistelmä, joka yksilöi tehdyn muutoksen (tätä voi käyttää tietyn muutoksen poistoon)
Ylimpänä näkyy sen jälkeen tekemäni muutos, johon kirjoitin kommentiksi "Added first steps to README"

Tämän jälkeen lisäsin tiedostoon lisää tekstiä, tallensin sen, mutta en lisännyt sitä git add, vaan kokeilin `git diff` komentoa.
Tämä antoi tiedon siitä, mitä muutoksia tiedostoon on tehty, joita ei ole lisätty.
**(kuva2)**

Rivejä tulkittaessa ilmeisesti kerrotaan, mitä tiedostoja verrataan, eli on a ja b "versio" tiedostoista, toinen on tallennettu toinen on jo lisätty, ja a on se, johon verrataan ja b se johon on lisätty.
Tässä versionhallinnassa oleva tiedostossa oleva on harmaalla, ja erot koneella olevaan tiedostoon ovat vihreällä, eli ne mitkä kirjoitin, mutta en vielä lisännyt versionhallintaan.

Tässä kohdassa annoin myös komennon `git blame README.md` joka antoi tiedot siitä, kuka on tehnyt muutoksia tiedostoon.
**(kuva 3)**

Tässä näkyy muutokset tiedostoon rivi kerrallaan aina kloonauksesta asti, eli originaali on GitHub käyttäjänimeni, sieltä on jäänyt otsikko tiedostoon, seuraavat muutokset olen tehnyt minä, lisännyt tekstiä tiedostoon ja myös tehnyt commitin, josta tullut kirjainyhdistelmä ja nimeni rivien alkuun, sekä aika, milloin tehty.
Kuvassa näkyy myös kirjoittamani teksti, jota en ole lisännyt addilla, rivillä lukee 00000000 Not Committed Yet, mutta myös aika milloin nämä tehty. Tästä voisi päätellä, että muutokset tosiaan tehty tiedostoon, mutta ei vielä lisätty versiohallintaan.

Tämän jälkeen tallensin tiedoston, ja tein uuden commitin varmuuden vuoksi, jonka jälkeen kokeilin tehdä tiedostoon tyhmää muutosta.

Kirjoitin tiedostoon tekstin "TYHMÄ MUUTOS TÄHÄN", ja lisäsin sen versionhallintaan. Tämän jälkeen annoin komennon `git reset --hard`, joka ei kysellyt mitään, vaan teki käskettyään, ja ilmoitti että HEAD on nyt versionumerossa 292b679, joka on commit, jonka tein ennen tyhmää muutosta kommentilla Added text up to silly change.**(kuva 4)**

Lisäsin ja committasin tiedoston tässä välissä, ja vein sen GitHubiin komennolla `git push`. Osoite oli sama mistä se oli kloonattu, joten kysyttiin GitHub käyttäjänimeä ja salasanaa, jolla pushataan, jotka annoin. Siirto onnistui ilman virheilmoituksia, ja raportti näkyi GitHubissa.
Tein vielä muutaman muutoksen selaimen kautta tiedostoon, ja kokeilin myös `git pull` komentoa, joka kertoi, että tiedostossa oli muutoksia, ja kuinka monta, ja että uusi tiedosto koneella on nyt se netistä pullattu.

# Uusi salt- moduli

Sitten tein uuden Salt- modulin, jossa asensin orjalle htop seurantaohjelman, ja muutin sen perusasetuksia artikkelin https://haydenjames.io/htop-quick-guide-customization/ mukaiseen muotoon.
Tässä ilmeisesti hyvät asetukset palvelinten admineille. Tein uuden kansion **/srv/salt/htop**, jonne tiedoston **init.sls*;

**(kuva 5)** ja lisäsin tiedoston, jota seurata **(kuva 6)**

ajoin tilan;

**(kuva 7)**

Tämä asensi htop ohjelman, ja muutti sen ulkonäköä, missä järjestyskessä tiedot ovat, mitä näytetään ja miten.


