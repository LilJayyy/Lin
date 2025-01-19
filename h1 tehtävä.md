# Raportin kirjoittaminen
- Täsmällistä raporttia tehdessä pitää selittää selkeästi mitä komentoja antoi. On tärkeää myö muistaa kellonajat, joka kertoo lukijalle työvaihesiin kuluvan ajan.
- Vikatilanteet ja virheilmoitukset pitää ilmaista selkeästi.
- Aikamuodon on oltava menneessä aikamuodossa.
- Raportin pitää olla helppolukuinen ja toistettava.
- Pitää oikeasti tehdä tehdyt testit, eikä sepittää.
- Kuvien luvaton kopiointi ei ole sallittua.
- Lähteet tulee kirjoittaa selkeästi akateemisia käytäntöjä noudattaen, jolloin perehtyminen aihealueeseenkin tulee ilmi.

LÄHTEET 

Karvinen, T. Artikkeli. 2006. Luettavissa: https://terokarvinen.com/2006/raportin-kirjoittaminen-4/ Luettu 19.1.2025.

# What is free software

- Free Softwarella tarkoitetaan vapaasti käytettävää ja muokattavaa ohjelmistoa, jota voi myös jakaa ilman rajoituksia.

- "Free" ei tarkoita tässä tapauksessa ilmaista, vaan oikeuksia käyttää, jakaa ja muokata ilman rajoituksia.

Neljä vapautta tarkoittaa

1. Vapaus käyttää ohjelmistoa kuten haluaa minkälaiseen käyttötarkoitukseen tahansa.

2. Vapautta opiskella/tutkia, sekä muokata toimivuutta oman käyttötarkituksen mukaan.

3. Vapautta ohjelmiston kopioiden levitykseen auttaen muitakin käyttäjiä samalla

4. Vapautta levittää itse muokattuja kopioita ohjelmistosta ja auttaen muita käyttäjiä. Tärkeää on muistaa lähdekoodin jakaminen.

LÄHTEET 

Free SW. Artikkeli. Luettavissa: https://www.gnu.org/philosophy/free-sw.html Luettu 19.1.2025.

# h1 Tehtävän raportti
Lähdin tekemään tehtävänantoa kotona sunnuntaina kello 15.05. VirtualBoxin asensin jo 14.1. tiistaina. Haasteena koin alkuun Virtualboxin käyttöliittymän, joka ei ole entuudestaan tuttu. Tietokoneeni on Fujitsu Lifebook E549 (Intel(R) Core(TM) i5-8265U CPU @ 1.60GHz  1.80 GHz).
Useampaa välilehteä kannattaa pitää auki asennusprosessin aikana. Avasin ohjeen tehtävänannosta, joka vei Debianin asentamiseen Virtualboxilla (Karvinen, T. 2021).  

Ensin piti kuitenkin asentaa virtuaalikone, jossa tein virheen. Hyppäsin suoraan Debianin asentamiseen. Onneksi tämä tuli huomattua alkuvaiheella. 
Huomasin ohjeessa edetessä, että Debian olisikin pitänyt asentaa ennen virtuaalikoneen luomista. Kello oli jo 15.40, joten mielessä ollut ”Lyhyt” asennus olikin ajateltua pidempi. 

## Virtuaalikoneen asennus
Virtuaalikoneen buuttausta edelsi asennustietojen määrittely virtuaalikoneeseen, jossa valittiin Debian (64-bit), tyypiksi Linux, muistin kooksi 4000Mb, prosessorien määräksi 4 ja luotiin virtual hard disk. Tiedoston kooksi valittiin 60GB, Hard disk file tyypiksi VDI (Virtualbox Disk Image) ja dynamically allocated valiten. Virtuaalikone ilmestyi tämän jälkeen Virtualbox Manageriin.

![Kuva1 h1](https://github.com/user-attachments/assets/d2f944b4-2781-4c00-a69f-4aa0e548ac8d)

Klikkasin hiiren oikealla asetukset (settings) auki ja menin kohtaan "Storage". Valitsin Controller: IDE kohdasta CDROM "Empty" kohdan. Sieltä klikkasin Attribuuteista cd-levyn kuvakkeesta auki uuden ikkunan, jossa valitsin Virtual Optical Disk Fileksi aiemmin asennetun ja tallennetun ISO Disk imagen (debian-live-12.9.0-amd64-cinnamon.ISO).

Tuplaklikkasin ohjeistuksen mukaisesti uuden virtuaalikoneen auki Virtualboxista, jonka asensin ohjeistuksen mukaisesti. Mutta tässä kohtaa tulikin virheilmoitus: ”Not in a hypervsor partition.” ”VT-X is disabled in the BIOS fo all CPU modes” (VERR_VMX_MSR-ALL_VMX_DISABLED).
Lähdin etsimään tietoa virheilmoituksen koodin perusteella Googlesta. Löysin Youtubesta hyvän ohjeen, miten enabloidaan virtualisointi Windows 11:lla. (Youtube, Bluestacks. 2021). 

Vikatilanteen korjaaminen onnistui hienosti virhekoodilla etsimällä ja videoa seuraamalla. Pääsin etenemään tehtävässä ja virtuaalikone käynnistyi hienosti.

Kohtasin ongelman, kun musta ruutu ilmestyi. Jouduin boottaamaan virtuaalikoneen uudestaan. Avasin virtuaalikoneessa ensin Live system (amd64) mutta resetoin virtuaalikoneen ja kokeilin käynnistää Live system (amd64 fail-safe mode), joka onnistui hienosti odottelun jälkeen, joten palasin takaisin boottaamaan Live system (amd64) onnistuneesti. Kyseessä olikin vain viive.

![Kuva3 h1](https://github.com/user-attachments/assets/30db276e-0f68-43c9-9c36-e1605d673f89)

Lähdin testaamaan virtuaalikoneen toimivuutta avaamalla selaimen ja Googletin ohjeistuksen mukaisesti ”Tero Karvinen” ja hakutulos aukesi onnistuneesti. Kello oli tässä vaiheessa 16.27 joten voisi sanoa, että asennusprosessin nopeaa etenemistä ei kannata olettaa ja on tärkeää varautua mahdollisiin virhetilanteisiin. 

## Debian GNU/Linux installer
Oli aika edetä Debian GNU/Linux Installerin pariin klikkaamalla työpöydän ”Install Debian” -kuvaketta. Lokaatioksi valitsin Finland, Kieleksi valitsin American English, Keybordiksi ”Generic 105-key PC (intl.).
Seuraavalle sivulle edetessä klikattin Erase disk: Yes, Encrypt: No, Boot loader location: ”Master Boot Record..” Valitsin nimeksi oman koko nimeni, kirjautuminimeni, tietokoneen nimen, kuitenkin poistaen oman nimi tietokoneen nimestä, sillä siitä tulee myös Public Domain nimi ja lopuksi vielä salasana ja jätetään automaattinen sisäänkirjautuminen tyhjäksi. Lopuksi klikattiin ”Install” napista. Asennusvaihe kesti noin viisi minuuttia. Lopuksi klikkasin ”Restart now” -nappulaa.

Käynnistymisessä meni hetki ja seuraavaksi syötettiin luotu käyttäjätunnus ja salasana. Kirjautuminen onnistui hienosti. Avasin jälleen Mozilla Firefox selaimen testaten toimivuutta onnistuneesti. 

## Terminal ja komennot tehtäviin päivityksiin
Lähdin avaamaan Terminaalin käynnistyspalkin ikonista ja syötin komennon sudo apt -get update. Salasanan syöttämisen jälkeen päivittämisprosessi lähti käyntiin. 
Syötin komennon sudo apt-get -y dist upgrade eli päivitetään kaikki. 

Virhetilanne tosin tuli jälleen, kun syötin ylimääräisen välilyönnin komentoon. Klikkasin nuolta ylöspäin, jolla sain kopioitua koko komennon ja poistin välilyönnin välistä, ja päivittäminen alkoi, jossa meni hetki. 
Asensin tämän jälkeen palomuurin komennoilla: sudo apt-get -y install ufw ja sudo ufw enable. Sain vahvistuksen onnistuneeseen asennukseen tekstillä ”Firewall is active and enabled on system startup”. 

Lopuksi tein vielä uudelleenkäynnistyksen käynnistys navigointipalkin vasemmasta kuvakkeesta. Kirjauduin sisään tunnuksilla ja olimmekin päässeet tämän harjoituksen loppuun. Linuxin asennus oli onnistunut. Kello oli tässä kohtaa 17.10. 

![Kuva4 h1](https://github.com/user-attachments/assets/4ac4e746-42a5-48a2-9f1a-9002af51043a)

Lopputulos

## Lähteet 

Bluestacks. Video. Youtube Enable Virtualization on Windows 11.
Katsottavissa: https://www.youtube.com/watch?v=t8f-zw_wcWM

Karvinen, T. 2021. Install Debian on Virtualbox. Luettavissa: https://terokarvinen.com/2021/install-debian-on-virtualbox/ Luettu: 19.1.2025.

Debian install. Luettavissa: https://cdimage.debian.org/debian-cd/current-live/amd64/iso-hybrid/ Luettu 19.1.2025.
