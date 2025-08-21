# Raportin kirjoittaminen

- Täsmällisyys selittäen selkeästi mitä komentoja on antanut ja tarkat kellonajat työvaiheisiin kuuluvasta ajasta.
- Helppolukuisuus väliotsikoita käyttäen ja kirjoita huolellista kieltä.
- Toistettavuus eli jos antaa raportin toiselle opiskelijalle pitää sama tulos tulla harhapolkuineen.

**LÄHTEET**  

Karvinen, T. Artikkeli. 2006. Luettavissa: https://terokarvinen.com/2006/raportin-kirjoittaminen-4/ Luettu 20.8.2025

# h1 Tehtävän raportti
Aloitin asentamisen 20.8.2025 kello 19.30. Tietokoneeni on Fujitsu Lifebook E549 (Intel(R) Core(TM) i5-8265U CPU @ 1.60GHz  1.80 GHz). 
Ensiksi asensin virtuaalikoneen Virtualboxilla, jonka jälkeen asensin Debian/GNU Linuxin ISO -tiedostolla juuri luotuun virtuaalikoneeseen. 

Käytin asennuksessa uusinta saatavilla ollutta versiota, joka raportin tekohetkellä oli debian-live-13.0.0-amd64-xfce.iso, ja joka sisälsi Calamares-asennusohjelman.

Tässä tehtävänannossa hyödynsin sekä Karvisen (2021) että Heinosen (2025) ohjeita.

## Virtuaalikoneen asennus
Asennuksen jälkeen lähdin määrittelemään asetuksia. 

* Valitaan Debian (64-bit), tyypiksi Linux
* Muistin kooksi 4000Mb, 
* Prosessorien (CPU) määräksi 2
* 60GB Tiedoston kooksi
* Hard disk file tyypiksi VDI (Virtualbox Disk Image) 
* Valitaan dynamically allocated.

![virtual](kuvat/virtual.png)

Virtuaalikone ilmestyi tämän jälkeen Virtualbox Manageriin.

![kone](kuvat/kone.png)

Ylälaidan pinikkeesta valittiin "Settings"

* Valitaan "Storage". 
* Controller: IDE kohdasta CDROM "Empty".
* Attribuuteista CD-levyn kuvakkeesta valittiin Virtual Optical Disk Fileksi aiemmin asennetun ja tallennetun ISO Disk imagen (debian-live-13.0.0-amd64-kde.iso).

Avasin juuri asennetun virtuaalikoneen Virtualboxista. Tuli virheilmoitus: ”Not in a hypervsor partition.” ”VT-X is disabled in the BIOS for all CPU modes” (VERR_VMX_MSR-ALL_VMX_DISABLED). Syötin virhekoodin Googleen ja löysin Youtubesta, miten enabloidaan virtualisointi Windows 11:lla. (Youtube, Bluestacks. 2021). 

Virheilmoitus tuli jälleen. Virtuaalikoneen käynnistyminen epäonnistui, koska aiemmin ladattu ISO-tiedosto oli valittuna. Mikäli aiempi ISO -tiedosto on ladattu koneeseen, tulee valita virheilmoituksen alasvetovalikosta haluttu ISO -tiedosto (debian-live-13.0.0-amd64-kde.iso). 

![kuva5](kuvat/kuva5.png)

Lähdin testaamaan virtuaalikoneen toimivuutta avaamalla selaimen ja Googletin ohjeistuksen mukaisesti ”TeroKarvinen.com” ja hakutulos aukesi onnistuneesti. 

Seuraavaksi lähdin asentamaan Debiania juuri luotuun virtuaalikoneeseen.

## Debian GNU/Linux installer
Asensin Debianin Live ISO -tiedostolla (debian-live-13.0.0-amd64-kde.iso), joka toi käyttöön Calamares-asennusohjelman. Käytettävissä olisi ollut myös toinen asennustapa (debian-cd/...iso-hybrid/), mutta valitsemalla Live ISO:n päädyin käyttämään Calamaresia, jolla halusin edetä. 

![Calamares](kuvat/Calamares.png)

Lähdin Debian GNU/Linux Installerin pariin klikkaamalla työpöydän ”Install Debian” -kuvaketta. 
* Lokaatioksi  Finland
* Kieleksi valitsin American English
* näppäimistön kieleksi English US
* Keyboardiksi ”Generic 105-key PC (intl.).

![Kielivalinta](kuvat/Kielivalinta.png)

Seuraavalle sivulle edetessä klikattiin 
* Erase disk: Yes
* Encrypt: No, Boot loader location: ”Master Boot Record..”
* Valitsin nimeksi koko nimeni, username, hostname, salasana ja automaattisen sisäänkirjautumisen jätin tyhjäksi.
* Lopuksi klikattiin ”Install” painikkeesta.

Tämä asennusvaihe kesti noin viisi minuuttia. 

![salasana](kuvat/salasana.png)

![Asennus](kuvat/Asennus.png)

Asennuksen valmistuttua ruksin ”Restart now” -ruudun ja lopuksi vielä klikataan "Done" -painiketta.

![done](kuvat/done.png)

Käynnistymisessä meni hetken aikaa ja melkein luuli jo asennuksen epäonnistuneen. Kyseessä olikin vain viive, tässä kohtaa kannattaa siis odottaa, kunnes kone avautuu kunnolla. 

Avasin testiksi vielä Mozilla Firefoxin toimivuuden tarkistamiseksi, joka lähti toimimaan odotetusti.

## Terminal ja komennot tehtäviin päivityksiin ja asennukseen
Lähdin avaamaan Terminaalin käynnistyspalkin ikonista ja tässä vaiheessa asennusprosessi on kestänyt hieman alle tunnin. 

Syötin alkuun komennon ls -la joka lähti listaamaan tiedostot ja kansiot.
![Terminal](kuvat/Terminal.png)

Seuraavaksi syötin komennot:
* sudo apt-get update. 
* sudo apt-get -y dist-upgrade eli päivitetään kaikki.

Salasanan syöttämisen jälkeen päivittämisprosessi lähti käyntiin, tietenkin muutaman klassisen kirjoitusvirheen jälkeen - jota täytyi hetken ihmetellä.

Vaihe kesti muutaman minuutin.

Terminalissa jatkettiin vielä palomuurin asentamisella ja käynnistyksellä komennoilla:
* sudo apt-get -y install ufw
* sudo ufw enable

  Lopputulos näytti tältä onnistuneen asentamisen jälkeen
  
  ![fire](kuvat/fire.png)

Uudelleenkäynnistyksen aika, eli valitsein ylälaidan "Applications" -valikosta "Log out" ja lopuksi vielä "Restart".

Vielä käyttäjätunnuksilla kirjautuminen ja olimmekin päässeet tämän harjoituksen loppuun. Linuxin asennus oli onnistunut. Kello oli tässä kohtaa 21:30 jolloin raportti ja asennusprosessit vaiheineen ovat valmiita.

![Kuva4 h1](https://github.com/user-attachments/assets/4ac4e746-42a5-48a2-9f1a-9002af51043a)

Lopputulos

## Lähteet 
Bluestacks. Video. Youtube Enable Virtualization on Windows 11.
Katsottavissa: https://www.youtube.com/watch?v=t8f-zw_wcWM Katsottu: 20.8.2025.  

Debian install. Luettavissa: https://cdimage.debian.org/debian-cd/current-live/amd64/iso-hybrid/ 20.08.2025  

Heinonen, J. 2025. Update linux-20082025.md. Verkkosivusto. Luettavissa: https://github.com/johannaheinonen/johanna-test-repo/blob/main/linux-20082025.md/ Luettu 20.08.2025  

Karvinen, T. 2021. Install Debian on Virtualbox. Artikkeli. Luettavissa:https://terokarvinen.com/2021/install-debian-on-virtualbox/ Luettu 20.08.2025  



