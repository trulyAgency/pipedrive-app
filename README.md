# Truly Automations – Pipedrive-app

Truly Agencyn Pipedrive-appin (Truly Automations) käyttöliittymäsivut. Sivut julkaistaan GitHub Pagesilla ja upotetaan Pipedriveen custom paneleina.

- `panel.html` – henkilön kortin paneeli (napit esim. HeyReach-kampanjaan lisäämiseen ja pyynnön tila)

## Periaatteet

- **Ei salaisuuksia tähän repoon.** Repo on julkinen. Ei API-avaimia, tokeneita, client secretejä eikä asiakastietoja.
- **Logiikka on n8n:ssä.** Sivu vain näyttää n8n:n palauttamat napit ja lähettää painallukset n8n:ään.
- **Tunnistus:** Pipedrive antaa paneelille allekirjoitetun JWT-tokenin (`userId`, `companyId`, voimassa 5 min). Sivu välittää tokenin jokaisessa kutsussa, ja n8n tarkistaa sen appin client secretillä. Ilman voimassa olevaa tokenia n8n ei tee mitään.
- **Asiakaskohtaiset napit** (esim. "Lähetä Ossin LinkedIn connect -pyyntö") tulevat n8n:n data tablesta, joten sivua ei muuteta asiakkaiden takia.
- Muutokset PR:n kautta.

## Julkaisu

Settings → Pages → Deploy from a branch → `main` / `(root)`.
Paneelin osoite Pipedriven Developer Hubissa: `https://trulyagency.github.io/pipedrive-app/panel.html`

Dokumentaatio: context layerin blueprint `pipedrive_app_router`.
