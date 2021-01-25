

# Linux livetikun asennus (Harjoitus 1)
Niko Hukkanen **25.1.2021**
Haaga-Helia ammattikorkeakoulu
Kurssi: [Linux palvelimet](https://terokarvinen.com/2020/linux-palvelimet-2021-alkukevat-kurssi-ict4tn021-3014/) by Tero Karvinen
## Käytössä olevat laiteet

 - Lenovon Legion Y540 kannettava tietokone (Intel i7-9750H CPU, RAM 16GB, Nvidia GTX 1660 Ti GPU.)
 - Kingston DataTraveler 100 G3 64 GB

## Harjoituksen tarkoitus
Harjoituksen tarkoituksena on luoda USB-muistitikulle Linux livetikku, josta pystyisi boottaamaan Linuxin suoraan käyntiin live tilassa, tai asentamaan sen käytettävän laitteen kovalevylle.
## Harjoituksen aloitus
Tein itse ensimmäisenä vaiheena varmuuskopiot Lenovon kannettavan tietokoneen kovalevystä varmuuden vuoksi, myös sen takia koska aikaisemmasta varmuuskopioinnista on kulunut jo tovi. Varmuuskopiointi tapahtui siirtämällä itselleni tärkeitä tiedostoja käsin ulkoiselle kovalevylle.
Varmuuskopioinnin jälkeen hain Xubuntu 20.04 LTS ( Long term support) iso kuvan seuraavalta verkkosivulta https://xubuntu.org/download#lts.
Tämän jälkeen latasin seuraavan ohjelman [Rufus 3.13](https://rufus.ie/), jonka avulla luodaan boottaavia USB-tikkuja, ohjelma myös alustaa kyseisen USB-tikun. Toinen sopiva ohjelma tähän tarkoitukseen olisi ollut [UNetbootin](https://unetbootin.github.io/).

![rufus](https://github.com/nikhuk/linuxpalvelimet/blob/main/assets/xubuntu20.04.PNG?raw=true)

Livetikun luonti ohjelmalla oli helppoa ja olin jo aikaisemmin tehnyt Ubuntusta livetikun. Avasin Rufus ohjelman, ja tarkistin sen, että kaikki asetukset olivat oikein esim. file system kohdassa oli valittu FAT32 muoto. Tämän jälkeen siirsin ISO tiedoston Rufus ohjelmaan ja painoin START näppäintä ohjelman oikeassa alaosassa. Rufus loi tikun noin alle 20 minuutissa, tämän jälkeen livetikku oli valmis käyttöön.

## Käynnistys
Kun livetikku oli valmis käynnistin tietokoneen uudestaan ja siirryin BIOS asetuksiin painamalla FN+ F2 näppäimiä samaan aikaan. Vaihtaessani BIOS asetuksia otin kaikista oletusasetuksista varmuuden vuoksi kuvat puhelimella, jotta olisi helppo palata aikaisempiin toimiviin asetuksiin.
Ensimmäisellä kerralla kokeilin vaihtaa ainoastaan Boot orderia ja Secure bootin poistoa, siten että Linpus lite (KingstonDataTraveler 3.0) USB-tikku olisi ensimmäisenä boot orderissa. 
Tämän jälkeen käynnistin koneen uudelleen ja huomasin, että kyseisellä käynnistyksellä tapahtui virhe **ACPI ERROR** ja **ACPI BIOS ERROR**. Ruudussa näkyi myös jonkin näköinen graaffinen virheviiva kolmannella rivillä.
![kuvavirheesta](https://github.com/nikhuk/linuxpalvelimet/blob/main/assets/virhekoodit.jpg?raw=true)


Tämän jälkeen käynnistin koneen uudelleen, ja menin BIOS asetuksiin, jossa vaihdoin asetuksia seuraavanlaisesti: Boot mode vaihdettiin [Legacy support] modeen ja Boot priority [Legacy first], myös PXE boot to LAN vaihdettiin [Disabled] arvoksi.

![toimivatasetukset](https://github.com/nikhuk/linuxpalvelimet/blob/main/assets/toimivatbiosasetukset.jpg?raw=true)


Kun vaihdoin kyseiset asetukset käyttöön, sain ensimmäisen onnistuneen käynnistyksen. Tässä vaiheessa valitsin valikosta seuraavan vaihtoehdon (Try Xubuntu) ja pääsin sisälle Xubuntu käyttöjärjestelmään. Tässä vaiheessa jouduin vielä uudemman kerran valitsemaan "Try Xubuntu". Tämän jälkeen pääsin aloittamaan ns. käytön.
Kun sain koneen käynnistettyä, sen jälkeen en huomannut minkäänlaisia muita ongelmia käytössä tai ominaisuuksissa kun suoritin tätä kyseistä harjoitusta. 

## Koneen rauta
Komennolla sudo lshw -short -sanitize terminaaliin syötettynä, sain näkyviin koneen raudan tiedot.
![raudantiedot](https://github.com/nikhuk/linuxpalvelimet/blob/main/assets/Screenshot_2021-01-24_16-58-43.png?raw=true)

## Kolmen ohjelman asennus
Kun aloitin käytön liitin tietokoneeni langattomaan verkkoon, ja aloin etsimään itseäni kiinnostavia kolmea ohjelmaa verkosta. Löysin seuraavat ohjelmat VLC, Audacity ja Blender. Latasin VLC ja Audacityn sovelluskaupan kautta, ja blenderin terminaali komennolla sudo apt-get install blender.

## Audacity
Ohjelman asennus ja lataus onnistui ilman ongelmia sovelluskaupasta. Testasin kyseisen ohjelman toimivuuden äänittämällä hetken mikrofonilla ääntä ja toistamalla sitä. Tässä vaiheessa saatiin testattua myös mikrofonin toimivuus, sekä kaiuttimen toimivuus.
![Audacity](https://github.com/nikhuk/linuxpalvelimet/blob/main/assets/audacitygpl2.0+.png?raw=true?raw=true)

## Blender
Blenderin latauksessa ja asennuksessa käytin komentoa sudo apt-get install blender terminaalissa, ja sain asennettua kyseisen ohjelman terminaalin kautta ongelmitta. Testasin Blenderin toimivuuden ja se toimi moitteetta.
![Blender](https://github.com/nikhuk/linuxpalvelimet/blob/main/assets/blender.png?raw=true)

## VLC
Asensin kyseisen ohjelman "software" sovelluksen kautta, mistä voi ladata erilaisia sovelluksia suoraan. Asennuksen jälkeen kokeilin katsoa videon VLC ohjelmalla ja se toimi moitteetta. 
![VLC](https://github.com/nikhuk/linuxpalvelimet/blob/main/assets/vlc.png?raw=true)

## Asennettujen ohjelmistojen lisenssit
Kaikki yllä mainitut kolme ohjelmistoa käyttävät GNU GPL lisenssiä. Kyseinen lisenssi tarkoittaa sitä, että ohjelmistoja voidaan käyttää mihin tahansa käyttötarkoitukseen vapaasti, sekä niitä voidaan muokata vapaasti ja myös vapaasti jakaa muille osapuolille.

## Linux ja Windows ohjelmien vastikkeita toisillensa
|Windows| Linux | 	
|--|--|
| Microsoft Word |LibreOffice Writer  |
| Mozilla Firefox |Mozilla Firefox  |
| Adobe Photoshop |GIMP  |
| Windows Media Player |VLC  

**Käyttötarkoitukset**
1. Tekstinkäsittelyohjelma
2. Verkkoselain
3. Kuvanmuokkaus
4. Videon toistaminen

## Lähteet

 - https://terokarvinen.com/2020/linux-palvelimet-2021-alkukevat-kurssi-ict4tn021-3014/
 - https://xubuntu.org/
 - https://www.gnu.org/licenses/gpl-3.0.html
 - https://www.audacityteam.org/about/
 - https://www.blender.org/about/license/
 - https://www.videolan.org/legal.html 
 - https://rufus.ie/
 - https://unetbootin.github.io/
 
