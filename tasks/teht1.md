
# Linux livetikun asennus (tehtävä 1)

## Käytössä olevat laiteet

 - Lenovon Legion Y540 kannettava tietokone (Intel i7-9750H CPU, RAM 16GB, Nvidia GTX 1660 Ti GPU.)
 - Kingston DataTraveler 100 G3 64 GB

## Harjoituksen tarkoitus
Harjoituksen tarkoituksena on luoda usb-muistitikulle Linux livetikku, josta pystyisi boottaamaan Linuxin suoraan käyntiin, tai asentamaan sen toiselle laitteelle kovalevylle.
## Harjoituksen aloitus
Tein itse ensimmäisenä vaiheena varmuuskopiot Lenovon kannettavan tietokoneen kovalevystä varmuuden vuoksi, myös sen takia koska aikaisemmasta varmuuskopioinnista on kulunut jo tovi.
Varmuuskopioinnin jälkeen hain Xubuntu 20.04 iso kuvan seuraavalta verkkosivulta (https://xubuntu.org/download#lts).
Tämän jälkeen latasin seuraavan ohjelman [Rufus 3.13](https://rufus.ie/), jolla luodaan niin sanottu usb-livetikku. Toinen sopiva ohjelma tähän tarkoitukseen olisi ollut UNetboot.

![rufus](https://github.com/nikhuk/linuxpalvelimet/blob/main/xubuntu20.04.PNG?raw=true)

Livetikun luonti ohjelmalla oli helppoa ja olin jo aikaisemmin tehnyt Ubuntusta livetikun. Avasin Rufus ohjelman, tämän jälkeen siirsin ISO tiedoston Rufus ohjelmaan ja painoin START näppäintä ohjelman alaosasta. Rufus raksutti noin alle 30-40 minuuttia, tämän jälkeen livetikku oli valmis.

Kun livetikku oli valmis käynnistin tietokoneen uudestaan ja siirryin BIOS/UEFI asetuksiin painamalla FN+ F2 näppäimiä. Vaihtaessani BIOS/UEFI asetuksia otin kaikista oletusasetuksista varmuuden vuoksi kuvat puhelimella, jotta olisi helppo palata aikaisempiin asetuksiin.
Ensimmäisellä kerralla kokeilin vaihtaa ainoastaan Boot orderia, siten että Linpus lite (KingstonDataTraveler 3.0) USB-tikku olisi ensimäisenä. Tämän jälkeen käynnistin koneen uudelleen ja huomasin, että kyseisellä käynnistyksellä oli tullut virhe ACPI ERROR ja ACPI BIOS ERROR. Ruudussa näkyi myös jonkin näköinen graaffinen virheviiva.
(kuva virheestä)
![kuvavirheesta](https://github.com/nikhuk/linuxpalvelimet/blob/main/virhekoodit.jpg?raw=true)


Tämän jälkeen käynnistin koneen uudelleen, ja menin BIOS asetuksiin, jossa vaihdoin asetuksia seuraavanlaisesti: Boot mode= vaihdettiin [Legacy support] modeen. ja Boot priority [Legacy first]
(kuva BIOS BOOT ORDERISTA)

![toimivatasetukset](https://github.com/nikhuk/linuxpalvelimet/blob/main/toimivatbiosasetukset.jpg?raw=true)


Kun vaihdoin kyseiset asetukset käyttöön, sain ensimmäisen onnistuneet käynnistyksen. Tässä vaiheessa valitsin valikosta seuraavan vaihtoehdon (Try Xubuntu) ja pääsin sisälle Xubuntu käyttö järjestelmään. Tässä vaiheessa jouduin vielä uudemman kerran valitsemaan "Try Xubuntu". Tämän jälkeen pääsin aloittamaan ns. käytön. 
Kun aloitin käytön liitin tietokoneeni langattomaan verkkoon, ja aloin etsimään itseäni kiinnostavia kolmea ohjelmaa. Löysin seuraavat ohjelmat VLC, Audacity ja Blender. Latasin VLC ja Audacityn sovelluskaupan kautta, ja blenderin terminaali komennolla sudo apt-get install blender
## Koneen rauta
![raudantiedot](https://github.com/nikhuk/linuxpalvelimet/blob/main/Screenshot_2021-01-24_16-58-43.png?raw=true)
Ylläolevasta kuvasta selviää käytettävän kannettavan tietokoneen osien tiedot.
## Kolmen ohjelman asennus
Kun aloitin käytön liitin tietokoneeni langattomaan verkkoon, ja aloin etsimään itseäni kiinnostavia kolmea ohjelmaa. Löysin seuraavat ohjelmat VLC, Audacity ja Blender. Latasin VLC ja Audacityn sovelluskaupan kautta, ja blenderin terminaali komennolla sudo apt-get install blender

## Audacity
Ohjelman asennus onnistui ilman ongelmia. Testasin kyseisen ohjelman toimivuuden myös äänittämällä hetken mikrofonin kautta ääntä ja toistamalla sitä. Tässä vaiheessa saatiin testattua myös mikrofonin toimivuus, sekä kaiuttimen toimivuus.
![Audacity](https://github.com/nikhuk/linuxpalvelimet/blob/main/audacitygpl2.0+.png?raw=true)

## Blender
Blenderin latauksessa käytin komentoa sudo apt-get install blender, ja sain asennettua kyseisen ohjelman terminaalin kautta. Testasin Blenderin toimivuuden ja se toimi moitteetta.
![Blender](https://github.com/nikhuk/linuxpalvelimet/blob/main/blender.png?raw=true)

## VLC
Asensin kyseisen ohjelman "software" sovelluksen kautta, mistä voi ladata erilaisia sovelluksia suoraan. Asennuksen jälkeen kokeilin, sitä että kyseinen ohjelma toimii moitteetta. VLC toisti testivideon ilman ongelmia.
![VLC](https://github.com/nikhuk/linuxpalvelimet/blob/main/vlc.png?raw=true)

## Asennettujen ohjelmistojen lisenssit
Kaikki yllä mainitut kolme ohjelmistoa käyttävät GNU GPL lisenssiä. Kyseinen lisenssi tarkoittaa sitä että ohjelmistoja voidaan käyttää mihin tahansa käyttötarkoitukseen ilmaiseksi, sekä niitä voidaan muuttaa ilman lupaa ja myös vapaasti jakaa.

## Linux ja windows ohjelmien vastikkeita toisillensa
|Windows| Linux |
|--|--|
| Microsoft Word |LibreOffice Writer  |
| Mozilla Firefox |Mozilla Firefox  |
| Adobe Photoshop |GIMP  |



