# Storingsmelder
Arjen Kaekebeke


Een klein meldingensysteem voor storingen. Je meldt een storing via een
formulier, je ziet de openstaande meldingen in een lijst, en je sluit ze af als
ze opgelost zijn.

Deze applicatie is het startpunt voor **Cloud computing (B-UCLL-MGN13A)**. Je
werkt er het hele semester mee. De applicatie zelf verandert bijna niet, wat
verandert is hoe en waar ze draait.

---

## Wat er in deze repo zit

```
app.py              de applicatie
requirements.txt    de pakketten die ze nodig heeft
templates/          de HTML van de webpagina
Dockerfile          bouwt de image van de applicatie
compose.yaml        start de applicatie samen met postgesql
requirements.txt    de pakketen die ze nodig heeft
.dockerignore       bestanden die niet mee in de image gaan
.env.example        sjabloon voor .env, met de namen van de variabelen
.gitignore          bestanden die niet mee in Git gaan
README.md           waar je nu zit

.env zelf staat niet in de repo, want daar staat het wachtwoord van de database in. Je maakt hem zelf aan, zie hieronder
```

## WalkTrough
```
Wat heb je nodig:
Docker desktop (moet draaiend zijn)
Git

stap 1:
Je gaat de Git repository clonen naar een lokale folder van jouw keuze.

git clone https://github.com/arjen-kaekebeke/cloud-computing.git

stap 2:
Maak een nieuw bestand .env met de gegevens van .env.example
Open .env en vul de 3 waarden in
voorbeeld:
    POSTGRES_USER=storingsmelder
    POSTGRES_PASSWORD=kies-een-wachtwoord
    POSTGRES_DB=storingen

Je kiest de waarden zelf en laat geen enkele waarde leeg.

stap 3:
Check nog eens of jouw docker desktop draait
Open Windows Powershell
voer commando "docker compose up -d --build"

check of alles draait
voer commando "docker compose ps"
normaal staat er bij de db aan het einde healthy

stap 4:
Ga naar jou webbrowser en zoek op http://localhost:8000
dan krijg je normaal gezien een website, als je dit niet krijgt overloop de stappen van de readme nog eens.

stap 5:
Hier leg ik uit hoe je kan stoppen en opruimen
stoppen:
docker compose down
dit commando stopt alles en je meldingen blijven bewaard

docker compose down -v 
dit commando stop alles en je meldingen worden gewist.

```

