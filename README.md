# Uitbreiding en stijl verandering CtC Kaart
![image](https://user-images.githubusercontent.com/45001009/230912889-58ca15ed-eda6-4c73-ba45-9b7e2612f096.png)

![image](https://user-images.githubusercontent.com/45001009/230912984-dfd595fd-5d47-4e0d-a62a-747877d80097.png)


## Inhoudsopgave

  * [Beschrijving](#beschrijving)
  * [Gebruik](#gebruik)
  * [Kenmerken](#kenmerken)
  * [Installatie](#installatie)
  * [Licentie](#licentie)

## Beschrijving
Deze sprint zijn we verder gegaan met het uitbreiden van onze producten gebaseerd op de aangeboden user stories. Er is weer gebruik gemaakt van EJS, Express en JS om de algemene structuur van het product op te zetten en de style van de pagina is verandert naar de wensen van de opdrachtgever. Alle data wordt nog steeds opgehaald via een REST API en er wordt gebruik gemaakt van de POST methode om gebruiker gegenereerde content op te slaan.

## Gebruik

### User story: Als vervoerder wil een smart zone kunnen reserveren, zodat ik mijn plek kan bevestigen

De site wordt geopend op een google Maps kaart en een bijbehorende lijst. Deze lijst is opgebouwd met data gebaseerd op de bestaande smart zones die worden aangeboden door Coding the Curbs. Je kan vervolgens de smartzones selecteren om hun locatie te weergeven op de kaart met wat meer informatie en een optie voor en routebeschrijving. Je hebt ook de opties om je eigen locatie te weergeven en de gewoonlijke features van google maps zoals street view, satteliet modus, zoom etc.

Een nieuwe toevoeging is de reserveer functie, waarmee je een smartzone kan selecteren. Hier wordt om data gevraagd die je vervolgens kan opslaan door op de reserveer knop te klikken. In toekomstige versies kan deze data weer terug weergeven worden om de beschikbaarheid van smartzones te weergeven.

## Kenmerken
### Node
Node is een onderliggend framework dat er voor zorgt dat we server side code kunnen schrijven en gebruik kunnen maken van verschillende modules zoals Express en EJS.

### Express
We gebruiken Express als framework voor onze projecten. Met express kunnen we verschillende routes aanmaken waarin we content kunnen aanbieden als webpaginas. Ook kunnen we gebruik maken van een view engine doormiddel van Express om de opmaak van de HTML makkelijker te maken. Verder kan je statische bestanden aanbieden door een statische route aan te geven via express. Doormiddel van de statische mappen

![image](https://user-images.githubusercontent.com/45001009/225786527-0d9b018c-66f6-4832-a38a-f345acda4c6b.png)

### EJS
De view engine die we gebruiken is EJS. Hiermee kan je makkelijk templates van HTML maken terwijl je direct in combinatie hiermee JS kan gebruiken.

![image](https://user-images.githubusercontent.com/45001009/225786576-438c8f50-4bd2-428f-8e7d-49a7d4285bd8.png)


### POST
We maken gebruik van de HTTP POST methode om gebruik gegenereerde data naar de bestaande REST API te sturen. De POST methode wordt aangeroepen doormiddel van een form met de methode post en wordt afgehandeld in JS met een POST route die aangeeft waar en hoe de data terecht moet.

```
router.post('/', (request, response) => {
  postJson(url1, request.body).then((data) => {}
  
  async function postJson(url, body) {
  return await fetch(url, {
    method: 'post',
    body: JSON.stringify(body),
    headers: { 'Content-Type': 'application/json' },
  })
```

```
<form action="/" method="post">
```

### .ENV
.ENV of environment variables zijn over het algemeen variabelen die informatie opslaan die je niet in directe code wilt hebben. In de meeste gevallen zijn dit API keys, wachtwoorden of sensitieve data. Door .dotenv te installeren en hier een bestand voor te maken, heb ik bepaalde data in mijn project verstopt zodat toegang tot de geleverde API veiliger is.

```
require('dotenv').config()

const baseurl = `${process.env.API_URL}`;

```


## Installatie
Fork en clone de repo om de nodige bestanden lokaal op te slaan, check dubbel voor package.json en run npm install.

```
npm run dev => nodemon omgeving opstarten
npm start => standaard node omgeving opstarten
```

## Licentie

This project is licensed under the terms of the [MIT license](./LICENSE).
