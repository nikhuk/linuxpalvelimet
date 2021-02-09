# Linux Server Course - Linux palvelimet ict4tn021-3014
Tämän sivuston tehtävät ja sisältö pohjautuvat Tero Karvisen linux palvelin kurssiin.(https://terokarvinen.com/)


# Linux livetikun asennus (Harjoitus 1)
Niko Hukkanen **25.1.2021**

Haaga-Helia ammattikorkeakoulu

Kurssi: [Linux palvelimet](https://terokarvinen.com/2020/linux-palvelimet-2021-alkukevat-kurssi-ict4tn021-3014/) 

Kurssin opettaja: [Tero Karvinen](https://terokarvinen.com/)

## Käytössä olevat laiteet

 - Lenovon Legion Y540 kannettava tietokone (Intel i7-9750H CPU, RAM 16GB, Nvidia GTX 1660 Ti GPU)
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
Kaikki yllä mainitut kolme ohjelmistoa käyttävät GNU GPL lisenssiä. Tämä lisenssi on hyvin yleinen avoimen lähdekoodin ohjelmisttoissa käytetetyistä linseseistä. Kyseinen lisenssi tarkoittaa sitä, että ohjelmistoa voidaan käyttää ja tutkia vapaasti, sekä sitä voidaan muokata vapaasti. Ohjelmistoa voidaan myös vapaasti jakaa muille osapuolille, kunhan lähdekoodi ja lisenssi annetaan mukaan.

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
 - https://www.linux.fi/wiki/GNU_GPL
 - https://www.audacityteam.org/about/
 - https://www.blender.org/about/license/
 - https://www.videolan.org/legal.html 
 - https://rufus.ie/
 - https://unetbootin.github.io/


# Apache-weppipalvlin (H3)

Niko Hukkanen **8.2.2021**

Haaga-Helia ammattikorkeakoulu

Kurssi: [Linux palvelimet](https://terokarvinen.com/2020/linux-palvelimet-2021-alkukevat-kurssi-ict4tn021-3014/)

Kurssin opettaja: [Tero Karvinen](https://terokarvinen.com/)

## Apachen asentaminen

Aloitin asentamisen kirjoittamalla sudo apt-get update, ja tämän jälkeen ajoin varsinaisen asennus komennon sudo apt-get install apache2 -y.  Asennuksen jälkeen huomasin, ettei Apache ollut lähteny toimimaan halutulla tavalla. Firefox ilmoitti seuraavanlaisesti, että kyseinen sivusto ei ole saatavissa.

![unable](https://github.com/nikhuk/linuxpalvelimet/blob/main/assets/h3/localhostx.PNG?raw=true)

Syy: Apache ei ollut käynnistynyt, joten tässä vaiheessa se piti käynnistää uudelleen, jotta se lähti toimimaan. Tähän käytin komentoa $sudo systemctl restart apache2.

Tämän jälkeen sain Apachen toimimaan. Tässä vaiheessa pääsin kokeilemaan Apachea selaimella osoitteesta http://localhost. Apache näytti lähteneen toimimaan uudelleenkäynnistyksen jälkeen.

![apache](https://github.com/nikhuk/linuxpalvelimet/blob/adc4c257e7997e46ecdf4a14a5f4202fef34b162/assets/h3/apache.PNG?raw=true)

Seuraavaksi tein kansion polkuun /home/niko/public_html komennolla $ mkdir public_html ja kyseiseen paikkaa myös index.html tiedoston.
![indexhtml](https://github.com/nikhuk/linuxpalvelimet/blob/main/assets/h3/nikos.PNG?raw=true)


## Surffaa oman palvelimesi weppisivuja. Etsi Apachen lokista esimerkki onnistuneesta (200 ok) sivulatauksesta ja epäonnistuneesta (esim 404 not found) sivulatauksesta. Analysoi rivit.
Kuvan koodiriveiltä löytyy samankaltainen loppuosa, josta selviää käytetty selain ja tietoa siitä.
Koodin loppuosasta selviää tietoa käytetystä "user agentista". Tästä selviää se, että käytössä on Linux käyttöjärjestelmä, sekä Firefox selain v. 78.0.

Kuvan ensimmäisellä rivillä näkyy virhe **404**.

Virhe johtuu kirjoitusvirheestä, jonka loin itse hakemalla sivustoa localhost/~nikoo/ firefoxillla. Kyseistä sivustoa ei ole olemassa. Tämän vuoksi se ilmoittaa, ettei kyseistä sivustoa löydy.

![apachelog](https://github.com/nikhuk/linuxpalvelimet/blob/main/assets/h3/apacheloki.PNG?raw=true)

**304 ( Not modified)** Sivusto ei ole muuttunut viime latauskerran jälkeen ja se löytyy välimuistista, joten sitä ei tarvitse ladata uudelleen.

**200 (OK)**

Kolmannella rivillä näkyy onnistunut kerta.

## Tee virhe johonkin Apachen asetustiedostoon, etsi ja analysoi tuo rivi. Etsimiseen sopivat esimerkiksi Apachen omat lokit, syslog sekä ‘apache2ctl configtest’.

![apachectl2](https://github.com/nikhuk/linuxpalvelimet/blob/main/assets/h3/apache2ctl%20configtest.PNG?raw=true)

Kun kirjoitin komentoriville seuraavan komennon sudo apache2ctl configtest, sain seuraavan ilmoituksen.

> `AH00558: Could not reliably determine the server's fully qualified domain name`

Muuten config test ilmoitti "Syntax OK". Lisää tietoa virheestä löysin sivustolta [DigitalOcean](https://www.digitalocean.com/community/tutorials/apache-configuration-error-ah00558-could-not-reliably-determine-the-server-s-fully-qualified-domain-name).
## Kuinka monta eri HTTP Status:ta (200, 404, 500…) saat aiheutettua lokeihin? Selitä, miten aiheutit tilanteet ja analysoi yksi rivi kustakin statuksesta.
Aikaisemmassa kohdassa sain aikaan seuraavat HTTP status:ta
 **200**
Tämän sain aikaan siirtymällä localhost sivustolle tai erilliselle http://locahost/~niko sivustolle.
**304**
Tämä tapahtui siksi, koska olin jo aikaisemmin käynyt sivustolla, eikä sitä ollut päivitetty sen jälkeen. Niin kyseinen sivusto löytyi jo välimuistista.
**404**
Tämän virheen sain itse aiheutettua siten, että kirjoitin virheellisen URL-osoitteen, jota ei ole olemassa tällä palvelimella. http://locahost/~nikoo
![404](https://github.com/nikhuk/linuxpalvelimet/blob/main/assets/h3/404.PNG?raw=true)



## Vaihda Apachen oletussivu. Eli laita palvelimen etusivulla (ilman tildeä) näkyvä sivu niin, että alkuperäinen on jonkun käyttäjän kotihakemistossa ja voit muokata sitä ilman pääkäyttäjän oikeuksia.
Käytin tehdessäni tätä muutosta [Teron ohjetta](http://terokarvinen.com/2016/new-default-website-with-apache2-show-your-homepage-at-top-of-example-com-no-tilde/index.html?fromSearch=) vuodelta 2016.
Aloitin luomalla VirtualHost:in ja annoin sille nimeksi niko.conf.  Paikkaan /etc/apache2/sites-available/niko.conf .
Tämän jälkeen editoin kyseistä tiedostoa seuraavanlaisesti: 

     /etc/apache2/sites-enabled/niko.conf
        <VirtualHost *:80>
         DocumentRoot /home/niko/public_html/
         <Directory /home/niko/public_html/>
           Require all granted
         </Directory>
        </VirtualHost>

Seuraavaksi otin pois käytöstä aikaisemman default Virtualhostin komennolla sudo a2dissite 000-default.conf. 
Tämän jälkeen otin käyttöön uuden komennolla sudo a2ensite niko.conf.
Näiden komentojen jälkeen käynnistin Apachen uudelleen komennolla sudo service apache2 restart.

![valmis](https://github.com/nikhuk/linuxpalvelimet/blob/main/assets/h3/vhost2.PNG?raw=true)

Lopuksi muokkasin index.html sivua lyhyesti ja validoin sen osoitteessa. [http://validator.w3.org](http://validator.w3.org/). 
Muokattava index.html löytyy polusta /home/niko/public_html/index.html.

## Lähteet

 - https://terokarvinen.com/2020/linux-palvelimet-2021-alkukevat-kurssi-ict4tn021-3014/#h3
 - http://terokarvinen.com/2008/05/02/install-apache-web-server-on-ubuntu-4/index.html?fromSearch=
 - https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/304
 - https://www.digitalocean.com/community/tutorials/apache-configuration-error-ah00558-could-not-reliably-determine-the-server-s-fully-qualified-domain-name
 - http://terokarvinen.com/2016/new-default-website-with-apache2-show-your-homepage-at-top-of-example-com-no-tilde/index.html?fromSearch=
