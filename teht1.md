# Linux livetikun asennus (tehtävä 1)

## Käytössä olevat laiteet

 - Lenovon Legion Y540 kannettava tietokone (Intel i7-9750H CPU, Ram 16GB, Nvidia GTX 1660 Ti GPU.)
 - Kingston DataTraveler 100 G3 64 GB

## Harjoituksen tarkoitus
Harjoituksen tarkoituksena on luoda usb-muistitikulle Linux livetikku, josta pystyisi boottaamaan Linuxin suoraan käyntiin, tai asentamaan sen toiselle laitteelle kovalevylle.
## Harjoituksen aloitus
Tein itse ensimäisenä vaiheena varmuuskopiot Lenovon kannettavan tietokoneen kovalevystä varmuuden vuoksi, myös sen takia koska aikaisemmasta varmuuskopioinnista on kulunut jo tovi.
Varmuuskopioinnin jälkeen hain Xubuntu 20.04 iso kuvan seuraavalta verkkosivulta (https://xubuntu.org/download#lts).
Tämän jälkeen latasin seuraavan ohjelman [Rufus 3.13](https://rufus.ie/), jolla luodaan niin sanottu usb-livetikku. Toinen sopiva ohjelma tähän tarkoitukseen olisi ollut UNetboot.
(rufus kuva)![rufus](https://github.com/nikhuk/linuxpalvelimet/blob/main/xubuntu20.04.PNG?raw=true)
Livetikun luonti ohjelmalla oli helppoa ja olin jo aikaisemmin tehnyt Ubuntusta livetikun. Avasin Rufus ohjelman, tämän jälkeen siirsin ISO tiedoston Rufus ohjelmaan ja painoin START näppäintä ohjelman alaosasta. Rufus raksutti noin alle 30-40 minuuttia, tämän jälkeen livetikku oli valmis.

Kun livetikku oli valmis käynnistin tietokoneen uudestaan ja siirryin BIOS/UEFI asetuksiin.
Ensimäisellä kerralla kokeilin vaihtaa ainoastaan Boot orderia, siten että Linpus lite (KingstonDataTraveler 3.0) USB-tikku olisi ensimäisenä. Tämän jälkeen käynnistin koneen uudelleen ja huomasin, että kyseisellä käynnistyksellä oli tullut virhe ACPI ERROR ja ACPI BIOS ERROR. Ruudussa näkyi myös jonkin näköinen graaffinen virheviiva.
(kuva virheestä)
Tämän jälkeen käynnistin koneen uudellleen, ja menin BIOS asetuksiin, jossa vaihdoin asetuksia seuraavanlaisesti: Boot mode= vaihdettiin [Legacy support] modeen. ja Boot priority [Legacy first]



