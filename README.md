![poster](./poster.png)

# Solaris
En webbplats byggd med HTML, CSS & vanilla JS om vårt solsystem.

## UI
Förslag på UI hittar ni [här](https://www.figma.com/file/Snw8n1gba7Mbk6TCLEAB1A/JS-%2F-Solaris?node-id=0%3A1).

## API
**Base URL**
```
https://n5n3eiyjb0.execute-api.eu-north-1.amazonaws.com
```

**Methods**
|enpoint|method|desc|
|---|---|---|
|/keys|POST|returnerar en API nyckel.|
|/bodies|GET|returnerar alla stora himlakroppar i vårt solsystem.|


**Authentication**

API:et är låst med en API-nyckel. Alla GET-requests utan en sådan kommer generar en ```401```. 

För att få läsrättigheter måste du i din request bifoga headern ```x-zocom``` med en giltig API-nyckel. 

Ex. 

```js
let resp = await fetch('https://n5n3eiyjb0.execute-api.eu-north-1.amazonaws.com/bodies', {
    method: 'GET',
    headers: {'x-zocom', '<solaris-key-here>'}
})
```
**Godkänt**
```
API-nyckel/solaris-key: solaris-2ngXkR6S02ijFrTP
```

## Modell
|egenskap|datatyp|enhet|
|---|---|---|
|id|number|-|
|type|string|star & planet|
|name|string|namnet på himlakroppen|
|latinName|string|Latinska namnet på himlakroppen|
|rotation|number|Längd på dygn i antal *jorddygn* runt sin egen axel|
|circumference|number|Omkrets i km|
|temp|Object|Temperatur *day* och *night* i celcius.|
|distance|number|km från solen|
|orbitalPeriod|Number|Antal *jorddygn* runt solen|
|desc|string|Beskrivning av himlakroppen|
|moons|Array|Lista med månarnas namn|

### Exempel

```js
{
    id: 2,
    type: 'planet',
    name: 'Venus',
    latinName: 'Venus',
    rotation: 116,
    circumference: 38025,
    temp: {
        day: 430,
        night: -173
    },
    distance: 10820000,
    orbitalPeriod: 225,
    desc: 'Venus har ...',
    moons: []
}
```

## Bedömning

För *Godkänt*: 
+ All UI-design är gjord med CSS (bilder är inte tillåtna)
+ Koden innehåller kommentarer som förklarar 

För *Väl Godkänt*:
+ Samtliga kriterier för Godkänt är uppfyllda. 
+ Koden är uppdelad i moduler med en kommentar i varje modul som förklarar dess syfte.
+ API:nyckeln hämtas med metoden POST (den är *inte* hårdkodad)

## Inlämning

Inlämning sker via Azomo. Ladda upp ditt projekt på Github, gå sedan in på Azomo och kopiera in länken till ditt repo i modulen som heter Individuell examination. 

Inlämning senast: 1/3 kl. 23:59




