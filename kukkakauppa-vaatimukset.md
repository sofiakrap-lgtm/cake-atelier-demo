# Kukkakauppa – vaatimuslista (demo-verkkosivu)

> Tämä on **vaatimusmäärittely** kukkakaupan verkkosivulle, joka rakennetaan
> saman rakenteen päälle kuin olemassa oleva The Cake Atelier -tilauskakkusivu.
> Rakenne on lähes identtinen: vaihtuu vain toimiala (kakut → kukat), sisältö
> ja visuaalinen ilme. Tekninen pohja on sama: **HTML + CSS + vanilla JS**, ei
> frameworkia, ei build-vaihetta. Lähes kaikki muokattava sisältö keskitetään
> yhteen tiedostoon (`site.js`), kuten kakkusivulla.

---

## 1. Käsitekartta: kakkusivu → kukkakauppa

| Kakkusivu (nyt)      | Kukkakauppa (uusi)        |
| -------------------- | ------------------------- |
| Kakut                | Kukkakimput               |
| Maut                 | Kukkalajit                |
| Kakkukategoriat      | Kimppukategoriat          |
| Kakun rakentaja      | Kimpun rakentaja          |
| Kakkukurssit         | Kukkasidontakurssit       |
| Erikoiskakut         | Erikoissidonnat           |
| Tilauslomake         | Tilauksen tarjouslomake   |

Arvio: **80–90 % komponenttirakenteesta voidaan käyttää uudelleen.** Vain
sisältö (data/site.js), kuvat ja brändivärit (style.css `:root`) vaihtuvat.

---

## 2. Uudelleenkäyttö – mihin olemassa oleviin tiedostoihin tämä kytkeytyy

| Olemassa oleva tiedosto | Rooli kakkusivulla      | Vastine kukkakaupassa                  |
| ----------------------- | ----------------------- | -------------------------------------- |
| `index.html`            | Etusivu / hero          | Etusivu / hero (kukka-asetelma)        |
| `tuotteet.html`         | Verkkokauppa + suodatus | Verkkokauppa: kukkakimput + suodatus   |
| `tilaa.html`            | Räätälikakun tilaus     | Kimpun tilaus / räätälöinti            |
| `hintalaskuri.html`     | Hinnan laskenta         | Hintalaskuri → tarjouspyyntö           |
| `catering.html`         | Tarjouspyyntölomake     | Erikoistilausten tarjouslomake         |
| `galleria.html`         | Kuvagalleria            | Referenssigalleria (häät, tapahtumat)  |
| `tapahtumat.html`       | Kurssit / tapahtumat    | Kukkasidontakurssit / workshopit       |
| `meista.html`           | Yrityksen tarina        | Meistä-sivu                            |
| `myymala.html`          | Toimipiste              | Myymälä-sivu                           |
| `yhteystiedot.html`     | Yhteystiedot + kartta   | Yhteystiedot + kartta                  |
| `palvelut.html`         | Palvelut                | Palvelut / erikoissidonnat             |
| `site.js`               | Keskitetty sisältö      | Sama – tuotteet/kategoriat vaihdetaan  |
| `style.css` (`:root`)   | Brändivärit & fontit    | Sama – vaihdetaan kukkakaupan ilmeeseen|
| `main.js`               | Navi, haku, kori, lomak.| Sama logiikka sellaisenaan             |

---

## 3. Pääsivu (index.html)

**Hero-osio**
- Suuri tunnelmallinen kuva kukka-asetelmasta tai myymälästä
- Yrityksen slogan
- Lyhyt kuvaus
- CTA-painikkeet:
  - "Tilaa kukkia"
  - "Pyydä tarjous"
  - "Laske hinta"

**Hero-osion jälkeen**

### Esittely
- Lyhyt tarina yrityksestä
- Mitä palveluita tarjotaan
- Erikoistuminen

### Suosituimmat tuotteet (kortit)
- Kuva
- Nimi
- Hinta
- Tilaa-painike

### Erikoistilaukset
- Häät
- Yritystilaisuudet
- Hautajaiset
- Juhlakoristelut

### Workshopit
- Tulevat työpajat
- Kukkasidontakurssit
- Ilmoittautuminen

### Yhteystiedot
- Osoite
- Aukioloajat
- Kartta
- Yhteydenotto

---

## 4. Verkkokauppa (tuotteet.html)

Kukkakimput listataan ja suodatetaan. Kategorisointi useammalla akselilla:

### Tilaisuuden mukaan
- Häät · Syntymäpäivät · Valmistujaiset · Hautajaiset · Yritystapahtumat

### Tyylin mukaan
- Moderni · Romanttinen · Minimalistinen · Luonnonläheinen · Värikäs

### Värimaailman mukaan
- Valkoinen · Pastelli · Vaaleanpunainen · Punainen · Monivärinen

### Hinnan mukaan
- Alle 30 € · 30–50 € · 50–100 € · Yli 100 €

### Koon mukaan
- Pieni · Keskikokoinen · Suuri

> Sama haku-/suodatus-/korilogiikka kuin kakkusivun tuotteet.html:ssä.
> Suodattimet ajetaan tuotteen metatiedoista (kategoria/tyyli/väri/hinta/koko)
> samaan tapaan kuin kakkujen maut/koot nyt.

---

## 5. Erikoistilaukset-sivu (catering.html / palvelut.html)

- Kuvagalleria
- Referenssit
- Hääkoristelut
- Tapahtumat
- Yritysprojektit
- **Tarjouslomake** (sama mekaniikka kuin kakkusivun catering-tarjouspyyntö)

---

## 6. Hintalaskuri + tarjouspyyntö (hintalaskuri.html)

- Asiakas valitsee parametrit (esim. tilaisuus, koko, kukkalajit, lisät)
- Laskuri näyttää arvion hinnasta
- Arvion perusteella voi **lähettää tarjouspyynnön**
- Toimii kuten kakkusivun hintalaskuri – vaihdetaan vain parametrit ja hinnoittelu

---

## 7. Meistä-sivu (meista.html)
- Yrityksen tarina
- Kuvia tiimistä
- Arvot
- Työskentelytapa

## 8. Myymälä-sivu (myymala.html)
- Kuvia liikkeestä
- Aukioloajat
- Kartta
- Palvelut paikan päällä

## 9. Yhteystiedot (yhteystiedot.html)
- Lomake
- Puhelin
- Sähköposti
- Kartta

---

## 10. Erot kakkusivuun (mitä pitää oikeasti vaihtaa)

1. **Maut → kukkalajit.** "Makujen" tilalla on kukkalajit. Tietyistä kukista
   voidaan koota tietty kimppu (esim. valitse kukat → kimppu).
2. **Kategorisointi laajenee.** Kimput luokitellaan usealla akselilla: koko,
   hinta ja visuaalinen maailma (värikäs / yksivärinen / juhlallinen / arkinen).
3. **Workshopit säilyvät**, mutta sisältönä kukkasidontakurssit.
4. **Sisältö, kuvat ja brändi-ilme** vaihtuvat kokonaan (site.js, assets, :root).

Tekninen rakenne, navigaatio, komponentit, korit ja lomakelogiikka pysyvät.

---

## 11. Liite: geneerinen "blueprint"-prompti rakenteen abstrahointiin

Kun halutaan irrottaa tästä valmiista sivustosta toimialariippumaton runko,
jonka päälle voi tehdä kukkakaupan (tai leipomon, jooga-studion, ravintolan)
vain sisältöä ja ilmettä vaihtamalla, voi käyttää esim. tällaista promptia:

> Analyze this website's structure and architecture. Ignore all
> industry-specific content, images, texts, products and branding. Extract only
> the reusable website structure, page hierarchy, navigation, sections,
> components, user flows and functionality. Then describe how the same structure
> could be adapted to another business category while preserving the exact
> layout and user experience.

Tai tarkempi versio:

> I have an existing custom cake ordering website. I want to reuse the exact
> same website structure for a flower shop. Analyze the project and identify:
> page structure, navigation structure, reusable components, ecommerce
> functionality, filtering systems, inquiry forms, galleries, booking/workshop
> systems, user flows. Then create a generic blueprint that can be reused for
> any service-based or product-based small business website.

Idea: Claude abstrahoi koko sivuston rakenteen sen sijaan että keskittyisi
kakkuihin → saadaan valmis runko, jonka päälle vaihdetaan vain sisältö ja
visuaalinen ilme. Sama rakenne, eri toimiala – kuten design-järjestelmissä.
