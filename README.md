# StarCraft România — site-ul Cetății Xel'Naga

Site static, o singură pagină, fără dependențe externe. Se pune gratuit pe GitHub Pages
și e construit de la zero pentru un singur scop: să iasă primul pe Google la
**„starcraft romania"** și la rudele acestei căutări.

**Cost total: 0 lei. Pentru totdeauna, nu doar în primul an.**

---

## 1. Ce e în folder

| Fișier | La ce e |
|---|---|
| `index.html` | **Pagina publicată.** Generată — nu o edita direct. |
| `body.html` | Sursa: stilurile + tot conținutul. **Aici editezi.** |
| `head.html` | Sursa: titlu, descriere, Open Graph, date structurate JSON-LD. |
| `build.py` | Lipește `head.html` + `body.html` → `index.html`, `robots.txt`, `sitemap.xml`. |
| `fonts.py` | Descarcă fonturile local (rulat deja; refolosește-l doar dacă schimbi fonturile). |
| `fonts/` | Fonturile self-hosted, 167 KB. |
| `og.png` | Imaginea care apare când dai link pe Discord, Facebook, WhatsApp. |
| `og-source.html` | Sursa imaginii de mai sus, dacă vrei s-o schimbi. |
| `favicon.svg` | Iconița din tab. |
| `404.html` | Pagina de eroare. |

**Fluxul de lucru:** editezi `body.html` (sau `head.html`) → rulezi `python3 build.py` → dai push.

---

## 2. Adresa gratuită — și de ce numele contului contează enorm

GitHub Pages îți dă o adresă gratuită, pe viață, fără card și fără reînnoire. Partea pe care
majoritatea o ratează: **adresa e chiar numele contului**. Un cont numit `starcraftromania`
îți dă `starcraftromania.github.io` — adică ai cuvintele-cheie chiar în adresă, gratis.

Am verificat pe 22 august 2026 — următoarele nume sunt **libere** pe GitHub:

| Nume cont | Adresa rezultată |
|---|---|
| `starcraftromania` | `starcraftromania.github.io` ← **recomandat** |
| `sc2romania` | `sc2romania.github.io` |
| `starcraft-romania` | `starcraft-romania.github.io` |
| `cetateaxelnaga` | `cetateaxelnaga.github.io` |

Fă-l ca **organizație**, nu ca al doilea cont personal: rămâi pe contul tău, iar la organizație
poți adăuga și alți moderatori ca owneri. New → New organization → planul **Free**.

> **Se poate clasa un `.github.io`?** Da. `github.io` e pe Public Suffix List, deci Google
> tratează fiecare `ceva.github.io` ca site de sine stătător, nu ca subpagină a GitHub.
> Un domeniu `.ro` ar ajuta la încredere și la rata de click, dar nu e obligatoriu ca să câștigi
> o căutare pe care concurența e adormită. Ce contează mai mult: conținut, viteză, linkuri.

`build.py` e deja setat pe `https://starcraftromania.github.io`. Dacă alegi alt nume, schimbă-l
acolo și rulează din nou scriptul.

---

## 3. Publicarea (~10 minute, zero lei)

1. Creezi organizația cu numele ales (vezi mai sus).
2. În ea, **New repository** cu numele **exact** `starcraftromania.github.io`
   — adică `<numele-organizației>.github.io`. Trebuie să fie *Public*.
3. Urci **conținutul** folderului, nu folderul în sine: `index.html` trebuie să ajungă în
   rădăcina repo-ului. (*Add file → Upload files*, sau cu git.)
4. **Settings → Pages** → *Source: Deploy from a branch* → branch `main`, folder `/ (root)` → Save.
5. Un minut mai târziu site-ul e live la `https://starcraftromania.github.io/`.

```bash
git init && git add . && git commit -m "Site-ul Cetatii"
git branch -M main
git remote add origin https://github.com/starcraftromania/starcraftromania.github.io.git
git push -u origin main
```

> **De ce contul, și nu un repo obișnuit?** Un repo normal ar da
> `user.github.io/nume-repo/`, iar pagina folosește căi absolute (`/fonts/…`, `/og.png`),
> care s-ar rupe. Repo-ul `<nume>.github.io` servește din rădăcină. Contează.

**Singurul lucru pe care trebuie să-l schimbi înainte de push:** linkul de Discord din
`build.py`. Acum e `discord.com/channels/…`, care merge doar pentru cine e deja membru.
Îți trebuie o invitație permanentă: click dreapta pe canal → *Invite People* →
*Edit invite link* → **Expire after: Never**, **Max uses: No limit**. O pui în `build.py`,
rulezi `python3 build.py`, gata.

---

## 4. Dacă vrei totuși o adresă mai frumoasă, tot pe gratis

Niciuna nu e obligatorie. Site-ul funcționează și se clasează și fără.

**a) GitHub Student Developer Pack** — ești deja student verificat (ai luat Azure for Students
pe adresa de la unibuc). Pachetul include un domeniu gratuit **pentru un an**:
Name.com dă `.live`, `.dev`, `.app`, `.studio`, `.software` ș.a.; Namecheap dă un `.me`;
mai e și un `.tech`. Un `starcraftromania.live` ar arăta foarte bine.
**Atenția**: după primul an se reînnoiește la preț întreg și cardul rămâne pe cont — dacă îl
iei, dezactivează auto-renew imediat. Deci nu e „gratis pe viață", e „gratis anul ăsta".

**b) `.eu.org`** — gratuit pe viață, administrat de o organizație non-profit, fără reclame.
Ceri un `sc2romania.eu.org` la nic.eu.org; aprobarea e manuală și poate dura zile.

**c) `.is-a.dev`** — gratuit pe viață, se cere printr-un pull request pe GitHub, se aprobă
repede. Dezavantaj: „is-a-dev" sună a portofoliu de programator, nu a comunitate de gaming.

**Ce NU mai există:** Freenom (`.tk`, `.ml`, `.ga`, `.cf`, `.gq`) și-a închis serviciul gratuit
la începutul lui 2024, după procesul cu Meta. Dacă vezi un site care încă îl recomandă, e vechi.

**Important dacă schimbi adresa mai târziu:** o mutare după ce ai strâns linkuri și poziții te
costă timp și cere redirecționări. Alege acum și rămâi acolo. Recomandarea mea: pornește pe
`starcraftromania.github.io` și nu-l mai schimba — e gratis, e permanent, are cuvintele-cheie
în adresă și nimeni nu ți-l poate lua.

---

## 5. Ce faci în ziua în care site-ul e live

Ordinea contează. Fără pasul 1 nu se întâmplă nimic — Google nu ghicește că exiști.

1. **Google Search Console** ([search.google.com/search-console](https://search.google.com/search-console))
   → adaugi proprietatea de tip *URL prefix* cu `https://starcraftromania.github.io/`
   → verifici cu metoda *HTML file* (urci fișierul primit în repo) sau *HTML tag*
   → *Sitemaps* → trimiți `sitemap.xml` → *URL Inspection* pe pagina principală → **Request Indexing**.
2. **Bing Webmaster Tools** — 5 minute, importă direct din Search Console. Bing alimentează și DuckDuckGo.
3. **Linkuri către site.** Ăsta e factorul pe care nu-l pot pune eu în cod și care decide
   clasarea. Fiecare loc de mai jos e un link legitim, nu spam:
   - descrierea și „About" ale serverului de Discord
   - descrierea canalului de Twitch / YouTube al fiecăruia care transmite
   - semnătura pe forumuri, profilul de Reddit, un post în `r/starcraft` sau `r/Romania`
     când ai ceva real de anunțat (un turneu, nu „uite site-ul meu")
   - grupurile de Facebook „Starcraft 2 Romania" — acolo sunt deja oamenii
   - Liquipedia, dacă organizezi un turneu care merită o pagină
4. **Nu cumpăra linkuri.** Pe o nișă atât de mică, un profil de linkuri artificial e mai
   ușor de detectat decât oriunde altundeva, iar o penalizare se repară în luni.

---

## 6. Ce e realist

Ce e deja rezolvat în pagină, la maximum: titlu și descriere scrise pe căutarea țintă,
un singur `H1`, structură semantică, date structurate `FAQPage` + `Organization` (calificare
pentru rezultate îmbogățite), `canonical`, `hreflang` pentru română, Open Graph și Twitter Card,
`sitemap.xml`, `robots.txt`, fonturi self-hostate cu preîncărcare pe elementul LCP, zero
cereri externe, zero JavaScript blocant, ~1.500 de cuvinte de conținut real în română.

Ce nu depinde de pagină: vechimea adresei, linkurile primite și cât de des e actualizat
site-ul. Realist, pe o căutare cu volum mic și concurență adormită, **prima pagină în câteva
săptămâni și primul loc în două-trei luni** e un obiectiv rezonabil. Nimeni nu poate garanta
poziția întâi — cine îți garantează, te minte.

Cel mai bun lucru pe care îl poți face după lansare e să nu lași pagina să înghețe. Exact
asta a omorât `starcraft.ro`, care n-a mai fost actualizat din octombrie 2021.

---

## 7. Următorul pas: clasamentul live pe site

Ai deja `king-of-kings.json` pe server. Dacă Curierul scrie periodic un fișier
`clasament.json` în repo (prin API-ul GitHub, cu un token), pagina îl poate citi și afișa
topul actualizat. Câștigi două lucruri deodată: conținut care se schimbă singur — semnal de
prospețime pentru Google — și un motiv real pentru care cineva revine pe site.

```js
// în pagină, la final:
fetch('/clasament.json')
  .then(r => r.json())
  .then(d => randeazaTop(d.top))   // d = { actualizat: "...", top: [{nume, sold}] }
  .catch(() => {});                // dacă lipsește, secțiunea rămâne ascunsă
```

---

Site de fani, gratuit, fără afiliere cu Blizzard Entertainment.
