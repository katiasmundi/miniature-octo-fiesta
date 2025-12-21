# The Final Document

## PortSwigger

### Suoritetut labrat 15 kpl

<img width="776" height="259" alt="image" src="https://github.com/user-attachments/assets/fa651338-d8c7-4baf-bf9c-89e70a3df2bf" />

Lista suoritetuista laboratorioista:
- SQL injection vulnerability in WHERE clause allowing retrieval of hidden data
- SQL injection vulnerability allowing login bypass
- Username enumeration via different responses
- Password reset broken logic
- Unprotected admin functionality
- User role can be modified in user profile
- Reflected XSS into HTML context with nothing encoded
- Stored XSS into HTML context with nothing encoded
- Stored XSS into anchor href attribute with double quotes HTML-encoded
- DOM XSS in document.write sink using source location.search
- DOM XSS in innerHTML sink using source location.search
- Detecting NoSQL injection
- Exploiting NoSQL operator injection to bypass authentication
- Exploiting an API endpoint using documentation
- Exploiting XXE using external entities to retrieve files


---

## The Booking System Project

### Phase 1
**Kuvaus:**  

Vaiheessa yksi piti tunnistaa mahdollisia haavoittuvuuksia varhaisessa kehitysvaiheessa, keskittyen rekisteröintitoiminnallisuuteen. Testaus tehtiin OWASP ZAP -työkalulla sekä manuaalitestauksella.

**Mikä toimi:**  

ZAP toimi, kunhan opetteli sen käytön.

**Mikä ei toiminut:**  

Burpin ilmainen versio jolla ensin yritin.

**Mikä vei eniten aikaa:**  

Testisyötteiden suunnittelu ja manuaalinen syöttäminen, jotta ZAP tunnisti injektoitavat kentät. Lisäksi piti tehdä raportti uusiksi, kun en ollut tajunnut laittaa active-ajoa päälle niin kaikkea ei löytynyt. Aikaa vei myös uusien työkalujen käytön opettelu. Myös itse raportin kirjoittaminen ja viiden tärkeimmän havainnon päättäminen oli työlästä ja haastavaa.

**Mitä opit:**  

ZAPin ja Docker Desktopin käyttöä. Paljon uutta testauksesta ja erilaisista tietoturvahavainnoista sekä niiden luokittelusta.

---

### Phase 2
**Kuvaus:**  

Vaiheessa kaksi käyntiin läpi autentikointia ja salasanojen käsittelyä. Mursin tässä viisi eri salasanaa käyttäen eri tekniikoita.

**Mikä toimi:**  

Työkalut kuten John the Ripper olivat tehokkaita työkaluja salasanojen murtamisessa.


**Mikä vei eniten aikaa:**  

Työkalujen (John the Ripper, wordlistit, säännöt) asentaminen ja konfigurointi. Yksittäisten, sanakirjan ulkopuolisten salasanojen murtaminen brute force -menetelmällä.

**Mitä opit:**  

Käytännön tasolla, että mikä ero on esim. lyhyellä ja pitkällä salasanalla sen murtamisen näkökulmasta. Ja kuinka hirveän helppoa on parissa sekunnissa murtaa huono salasana, joka on huonosti hashatty.

---

### Phase 3
**Kuvaus:**  

Vaiheessa kolme testattiin sovelluksen autorisointia ja roolipohjaista pääsynhallintaa. Tarkoituksena oli selvittää, vastaavatko järjestelmän backend-tason oikeudet käyttöliittymän rajoituksia. Suoritin testauksen manuaalisesti selaimella, OWASP ZAPilla sekä ffuf-työkalulla eri käyttäjärooleilla (guest, reserver ja administrator).

**Mikä toimi:**  

Tehtävänanto oli selkeämpi kuin aiemmat.

**Mikä vei eniten aikaa:**  

Jostain syystä tässä tuli paljon ongelmia ja aihe oli myös jotenkin haastavampi ymmärtää, joten kaikkeen säätöön meni aikaa. Lisäksi kone tilttasi ja jouduin aloittamaan alusta (Zapin). En myöskään meinannut hahmottaa millä työkalulla löydän piilotettuja endpointeja parhaiten.

**Mitä opit:**  

Piilotettujen endpointtien etsiminen on keskeinen osa autorisointitestausta. Autorisointi on toteutettava backendissä, eikä käyttöliittymän rajoituksiin voi luottaa. Ffuf:n käyttöä.

---
### Phase 4
**Kuvaus:**  

Vaiheessa neljä käytiin läpi varausjärjestelmää GDPR:n (ja Privacy by design:n) näkökulmasta. Kävin läpi, mitä henkilötietoja järjestelmä kerää, miten niitä käsitellään ja onko käyttäjien oikeudet (kuten tiedonsaanti ja tietojen poistaminen) huomioitu. Lisäksi tarkistin tietoturvakäytännöt sekä laadin puuttuvat dokumentit: Privacy Policy, Terms of Service ja Cookie Policy.

**Mikä toimi:**  

Henkilötietojen kartoitus oli melko suoraviivaista, koska tiedot löytyivät selkeästi tietokannasta ja lomakkeista. GDPR-checklist oli hyvä.


**Mikä vei eniten aikaa:**  

Järjestelmän muutosten tutkiminen (vs. phase 3).

**Mitä opit:**  

GDPR on aiheena tuttu, mutta nyt mietin sitä ensimmäistä kertaa järjestelmän ominaisuuksien kautta ns. suunnittelunäkökulmasta. Monia seikkoja pitää ottaa huomioon, eikä pelkkä rekisteröitymislomakkeen tutkiminen riitä.


---
### Reflection

The Booking System -projektin aikana opin ihan todella paljon uutta tietoturvasta ja testaamisesta. Opin, että penetraatiotestaus ei ole vain yksittäisten haavoittuvuuksien löytämistä, vaan vaatii ymmärrystä mm. sovelluksen toiminnasta, käyttäjärooleista ja autentikoinnista. Opin käyttämään työkaluja kuten OWASP ZAP, Ffuf ja John the Ripper ja lisäksi ymmärsin manuaalisen testauksen merkityksen. Lisäksi sain uutta näkökulmaa siihen, miten GDPR ja Privacy by Design eivät ole pelkästään dokumentaatiota, vaan vaikuttavat suoraan järjestelmän teknisiin ratkaisuihin.

---

## Logbook

### Git-repositorio

https://github.com/katiasmundi/miniature-octo-fiesta/new/main/BookingSystem/Phase1

(Kaikki Phase1:n alla, kun alussa oli vähän ristiriitaisia ohjeita niin jäivät nyt sinne.)

### Kurssiin käytetty aika

**Kokonaisaika:**  

- 60 tuntia

**Tunnit aiheittain:**

- The Booking system project: 30
- Muut aiheet: 30

---

## Feedback

Tehtävänannot olivat hiukan hajallaan ja pitkiä. Kesti aina aikaa löytää kunkin vaiheen ydin, ainakaan jos ei ollut malttanut katsoa tallennetta vielä ennakkoon. Näihin voisi kiinnittää huomiota, että tehtävän tavoite olisi heti tiivistettynä ytimekkäästi. Phaset 3-4 taisivatkin olla selkeämmät kuin aiemmat.
Ihan todella mielenkiintoinen kurssi. Syvensin osaamista juttelemalla ChatGPT:n kanssa, niin se alkoi jossain välissä vastailemaan, että ei pysty antamaan ohjeita niin tuhoaviin toimenpiteisiin (käyttäjän poistaminen tietokannasta). 
Mukava, kun opettaja käyttää oikeasti aikaa tehtävien tekemiseen ja tarkistamiseen. Plussaa, että ei tarvitse tehdä väkisin ryhmätyönä, niin oppii paljon enemmän.
Oli kyllä ihan hirveästi työtä, mutta jospa tästä jäi jotain mieleen sen vuoksi. :)
