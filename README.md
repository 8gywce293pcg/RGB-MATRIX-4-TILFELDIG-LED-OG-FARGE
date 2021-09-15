### @explicitHints false

## Introduksjon @unplugged
Her vil du lære å kode våre kule LED displayer. 
Målet er å få en tilfeldig LED til å blinke og med tilfeldig farge ved bruk av variabeler.


## Steg 1: Definer noen neopixler @fullscreen
 Trykk på ``||Neopixel:Neopixel||`` fra blokkmenyen.
 Klikk og dra inn blokken ``||Neopixel: sett strip til ||`` og slipp den inn i ``||basic: ved start ||`` blokken.
 Velg pinne ``||Neopixel: P0 ||`` og antall LED til ``||Neopixel: 768 ||`` la format stå som ``||Neopixel: RGB (GRB) ||``.
 Denne blokken brukes for å velge hvilken pinne som er koblet til LED, hvor mange LED det er og hvilken type LED. 

```blocks

let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)

```
## Steg 2: Slette minne i LED
Trykk på ``||Neopixel: Neopixel ||`` fra blokkmenyen.
Klikk og dra inn blokken ``||Neopixel: strip.clear ||`` plasser den under forrige blokk.
Denne blokken sletter tidligere data inni lysdidodene.

```blocks

let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()

```
## Steg 3: Lage en variabel for å få en tilfeldig LED til å lyse
Trykk på ``||Variabler: variabel ||`` fra blokkmenyen og klikk deretter ``||Variabler: lag en variabel ||`` og gi variabelen navnet ``||Variabler: TILFELDIG LED ||``.
Trykk på ``||Variabler: variabel ||``, klikk og dra blokken ``||Variabler: Sett TILFELDIG LED ||`` inn i ``||basic:gjenta for alltid||``.
Trykk på ``||Math: Matematikk ||`` klikk og dra inn ``||Math: velg tilfeldig 0 til 0 ||``.Sett denne inni blokken ``||Variabler: Sett TILFELDIG LED ||`` i verdien 0.
Sett Verdiene ``||Math: 0 til 767 ||``.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()
basic.forever(function () {
   TILFELDIG_LED = randint(0, 767)
})
```
## Steg 4: Lage en variabel for å få en tilfeldig farge
Trykk på ``||Variabler: variabel ||`` fra blokkmenyen og klikk deretter ``||Variabler: lag en variabel ||`` og gi variabelen navnet ``||Variabler: TILFELDIG FARGE ||``.
Trykk på ``||Variabler: variabel ||``, klikk og dra blokken ``||Variabler: Sett TILFELDIG FARGE ||`` inn i ``||basic:gjenta for alltid||``.
Trykk på ``||Math: Matematikk ||`` klikk og dra inn ``||Math: velg tilfeldig 0 til 0 ||``.Sett denne inni blokken ``||Variabler: Sett TILFELDIG FARGE ||`` i verdien 0.
Sett Verdiene ``||Math: 0 til 5 ||``.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()
basic.forever(function () {
   TILFELDIG_LED = randint(0, 767)
   TILFELDIG_FARGE = randint(0, 5)
})
```
## Steg 5: Sette opp en logikk for å sjekke tilfeldige Farge 1
Trykk på ``||Logic: Logikk||`` fra blokkmenyen og klikk og dra inn ``||Logic:hvis||`` og sett denne inn i ``||basic:gjent for alltid||`` under ``||Variabler: TILFELDIG_FARGE||``.
Trykk på ``||Logic: Logikk||`` fra blokk menyen og klikk og dra inn ``||Logic: < 0 = 0 > ||`` og sett denne inn i ``||Logic:hvis||``.
Trykk på ``||Variabler: Variabel||`` fra blokkmenyen og klikk og dra blokken ``||Variabler: TILFELDIG FARGE ||``  i første 0 inni  ``||Logic: < 0 = 0 > ||`` blokken.
og sett denne til ``||Logic: < TILFELDIG_FARGE = 0 > ||``.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()
basic.forever(function () {
   TILFELDIG_LED = randint(0, 767)
   TILFELDIG_FARGE = randint(0, 5)
    if (TILFELDIG_FARGE == 0) {
        
    } 
})
```
## Steg 6: Sette opp en logikk for å sjekke tilfeldige Farge 1 
Trykk på ``||Neopixel: Neopixel ||`` fra blokkmenyen og klikk deretter ``||Neopixel: mer ||``.
Klikk og dra inn blokken ``||Neopixel: strip set_Pixel_Color at 0 to Red ||`` plasser den inni ``||Logic: hvis ||`` blokken.
Trykk på ``||Variabler: Variabler ||`` deretter klikk og dra inn blokken ``||Variabler: TILFELDIG LED ||`` inn i  blokken ``||Neopixel: strip set_Pixel_Color at 0 to Red ||`` i verdien 0.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()
basic.forever(function () {
     TILFELDIG_LED = randint(0, 767)
     TILFELDIG_FARGE = randint(0, 5)
       if (TILFELDIG_FARGE == 0) {
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Red))   
    } 
})
```
## Steg 7: Sette opp en logikk for å sjekke tilfeldige Farge 2
Trykk på ``||Neopixel: Neopixel ||`` fra blokkmenyen og klikk deretter ``||Neopixel: strip show ||``.
Sett denne inn under ``||Neopixel: strip set_Pixel_Color at TILFELDIG LED to Red ||``

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()
basic.forever(function () {
     TILFELDIG_LED = randint(0, 767)
     TILFELDIG_FARGE = randint(0, 5)
       if (TILFELDIG_FARGE == 0) {
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Red))  
        strip.show() 
    } 
})
```
## Steg 8: Send informasjon til Neopixlene
Trykk på ``||basic: Basis ||`` fra blokkmenyen og klikk deretter ``||Basic: pause ||``.
Sett denne inn under ``||Neopixel: show ||`` og sett verdien til 100ms

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()
basic.forever(function () {
     TILFELDIG_LED = randint(0, 767)
     TILFELDIG_FARGE = randint(0, 5)
       if (TILFELDIG_FARGE == 0) {
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Red))  
        strip.show()
        basic.pause(100) 
    } 
})
```
## Steg 9: Send informasjon til Neopixlene
Ved å klikke på ``||Logic: + ||`` tegnet nede på ``||Logic: hvis ||`` blokken kan vi utvide Logikken til flere kontrollpunkter.
Du vil da få et felt som heter ``||Logic: ellers hvis ||``. 

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()
basic.forever(function () {
     TILFELDIG_LED = randint(0, 767)
     TILFELDIG_FARGE = randint(0, 5)
       if (TILFELDIG_FARGE == 0) {
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Red))  
        strip.show()
        basic.pause(100) 
    }  else if (false) {
    }
})
```



## Steg 10: Send informasjon til Neopixlene
Trykk på ``||Logic: Logikk||`` fra blokk menyen og klikk og dra inn ``||Logic: < 0 = 0 > ||`` og sett denne inn i ``||Logic: hvis ||``. 
Trykk på ``||Variabler: Variabel||`` fra blokkmenyen og klikk og dra blokken ``||Variabler: TILFELDIG FARGE ||``  i første 0 inni  ``||Logic: < 0 = 0 > ||`` blokken.
og sett denne til ``||Logic: < TILFELDIG_FARGE = 1 > ||``.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()
basic.forever(function () {
    TILFELDIG_LED = randint(0, 767)
    TILFELDIG_FARGE = randint(0, 5)
    if (TILFELDIG_FARGE == 0) {
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Red))
        strip.show()
        basic.pause(100)
    } else if (TILFELDIG_FARGE == 1) {
})
```
## Steg 11: Send informasjon til Neopixlene
Trykk på ``||Neopixel: Neopixel ||`` fra blokkmenyen og klikk deretter ``||Neopixel: mer ||``.
Klikk og dra inn blokken ``||Neopixel: strip set_Pixel_Color at 0 to Red ||`` plasser den inni ``||Logic: hvis ||`` blokken.
Trykk på ``||Variabler: Variabler ||`` deretter klikk og dra inn blokken ``||Variabler: TILFELDIG LED ||`` inn i  blokken ``||Neopixel: strip set_Pixel_Color at 0 to Red ||`` i verdien 0.
Skift farge til Orange. sett også inn ``||Neopixel: show ||`` og  ``||Basic: pause ||``.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()
basic.forever(function () {
    TILFELDIG_LED = randint(0, 767)
    TILFELDIG_FARGE = randint(0, 5)
 if (TILFELDIG_FARGE == 0) {
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Red))
        strip.show()
        basic.pause(100)
    } else if (TILFELDIG_FARGE == 1) {
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Orange))
        strip.show()
        basic.pause(100)
    } 
    })
```

## Steg 12: Send informasjon til Neopixlene
Gjenta utvidelsen av ``||Logic: hvis ||`` blokken slik at du sjekker variabelen ``||TILFELDIG FARGE ||`` opp til verdien 5.
Husk å skifte farge for hvert ``||Logic: ellers hvis ||``.
```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()
basic.forever(function () {
    TILFELDIG_LED = randint(0, 767)
    TILFELDIG_FARGE = randint(0, 5)
 if (TILFELDIG_FARGE == 0) {
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Red))
        strip.show()
        basic.pause(100)
    } else if (TILFELDIG_FARGE == 1) {
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Orange))
        strip.show()
        basic.pause(100)
    } else if (TILFELDIG_FARGE == 2) {
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Yellow))
        strip.show()
        basic.pause(100)
    } else if (TILFELDIG_FARGE == 3) {
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Green))
        strip.show()
        basic.pause(100)
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.White))
        strip.show()
    } else if (TILFELDIG_FARGE == 4) {
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Green))
        strip.show()
        basic.pause(100)
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Blue))
        strip.show()
    } else if (TILFELDIG_FARGE == 5) {
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Indigo))
        strip.show()
        basic.pause(100)
    }
    })
```
## Steg 13: Send informasjon til Neopixlene
Sett inn ``||Neopixel: Strip Clear ||`` og ``||Neopixel: strip show ||`` under ``||Logic: hvis ||`` blokken.
Disse blokkene er for å slå av lysdiodene igjen før neste tilfeldige LED og FARGE skal velges.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()
basic.forever(function () {
    TILFELDIG_LED = randint(0, 767)
    TILFELDIG_FARGE = randint(0, 5)
 if (TILFELDIG_FARGE == 0) {
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Red))
        strip.show()
        basic.pause(100)
    } else if (TILFELDIG_FARGE == 1) {
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Orange))
        strip.show()
        basic.pause(100)
    } else if (TILFELDIG_FARGE == 2) {
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Yellow))
        strip.show()
        basic.pause(100)
    } else if (TILFELDIG_FARGE == 3) {
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Green))
        strip.show()
        basic.pause(100)
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.White))
        strip.show()
    } else if (TILFELDIG_FARGE == 4) {
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Green))
        strip.show()
        basic.pause(100)
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Blue))
        strip.show()
    } else if (TILFELDIG_FARGE == 5) {
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Indigo))
        strip.show()
        basic.pause(100)
    }
    strip.clear()
    strip.show()
})
```


## Steg 19: Leste ned på microbiten

Hvis du har en @boardname@ tilkoblet, trykk ``|last ned|``! 

Prøv nå å lage en ``||Variabler: variabel ||`` og sett inn i ``||basic:pause(variabel)||`` for å endre hastighet kun med en variabel.
Hosk å sette inn ``||Variabler: sett varibel til ||`` blokk i ``||basic: ved start ||`` blokken.
For hver endring vi gjør i koden må det lastes ned på nytt til @boardname@.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()
pause = 10
basic.forever(function () {
    TILFELDIG_LED = randint(0, 767)
    TILFELDIG_FARGE = randint(0, 5)
 if (TILFELDIG_FARGE == 0) {
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Red))
        strip.show()
        basic.pause(pause)
    } else if (TILFELDIG_FARGE == 1) {
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Orange))
        strip.show()
        basic.pause(pause)
    } else if (TILFELDIG_FARGE == 2) {
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Yellow))
        strip.show()
        basic.pause(pause)
    } else if (TILFELDIG_FARGE == 3) {
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Green))
        strip.show()
        basic.pause(pause)
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.White))
        strip.show()
    } else if (TILFELDIG_FARGE == 4) {
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Green))
        strip.show()
        basic.pause(pause)
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Blue))
        strip.show()
    } else if (TILFELDIG_FARGE == 5) {
        strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Indigo))
        strip.show()
        basic.pause(pause)
    }
    strip.clear()
    strip.show()
})
```
