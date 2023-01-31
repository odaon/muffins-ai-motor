# muffins-ai-motor

Dette er et case for en maskinlæringsworkshop organisert av BRAIN NTNU og Fremtind Forsikring. Det er antatt at deltagerene har grunnleggende Python-kunskaper, og har installert Python 3.10 på datamaskinen sin.

## Introduksjon

Vi skal se på et datasett som inneholder utbetalingskrav for rapporterte skader på forsikrede kjøretøy. Noen av disse kravene ble oppdaget at var forsøk på svindel! Vi skal lage en maskinlæringsmodell som snuser ut fremtidig muffins blant de inrapporterte kravene, og markerer de som har ugler i mosen. Dette kalles en "binær klassifikasjonsoppgave", fordi maskinlæringsmodellen sin jobb er å dele inn alle kravene i to klasser, nemlig "misstenkt svindel" og "ikke misstenkt svindel". Dette kan en maskinlæringsmodell greie ved å lære seg hvilke datamessige fellestrekk identifiserte svindelsaker har hatt i fortiden. Men pass på, ikke all data er bra data, og noen ganger har valgene dine som maskinlæringsingeniør etiske konsekvenser for dem som blir påvirket av systemet: Greier du å identifisere og forutse forskjellige etiske konsekvenser av hvilke data du bruker, og hvordan du optimerer modellen din? Hvilke konsekvenser vil de ha å stole på en unøyaktig modell, og hvordan bør man i forskjellige tilfeller bruke den for å unngå negative konsekvenser?

Dataene våre har en salig kombinasjon av kategoriske data (som bilmerke) og kontinuerlig distribuerte data (som prisen på forsikringsobjektet), og noen av kravene mangler også noe av dataen. Det er din jobb som maskinlæringsingeniør å velge og massere dataene. Hva er bra og dårlig data? Hvilke kolonner skal du bruke, og hvordan skal de representeres eller kombineres når du sender dem inn i modellen din? Da lønner det seg å skjønne litt om hva slags maskinlæringsmodeller som fungerer for  forskjellig data, og hvordan kan du eventuelt kan trikse med data for å få den til å fungere bedre med en gitt modelltype.

## Praktisk

Dette er et git-repository. Det betyr at prosjektet med alt innhold er versjonskontrollert med verktøyet "git", som gjør det lett for flere mennesker å sammarbeide, oppdatere prosjektet, og hente prosjektet fra nettet.

Dette repositoriet inneholder nesten alt du trenger for å løse oppgaven på en grei måte. En forutsetning for å gjennomføre caset er at du har [Python](https://www.python.org/) (v3.10 er anbefalt) installert på datamaskinen din.

For å laste ned dette repositoriet til maskinen din kan du enten bruke kildekodeversjoneringsverktøyet [git](https://git-scm.com/), eller laste ned dette prosjektet som en zip-fil ved å klikke på den grønne [<>CODE]-knappen du ser over denne README-filen slik den vises på github.

Hvis du har git installert kan du gå åpne kommandolinjen i folderen du ønsker å lagre prosjektfolderen i og kjøre denne kommandoen for å kopiere hele prosjektet til maskinen din:

`git clone https://github.com/odaon/muffins-ai-motor.git`

Når du har prosjektfolderen på maskinen din kan du åpne kommandolinjen og kjøre

`python -m pip install pipenv`

Dette installerer en pakke som kan lage et ferskt virtuelt python-miljø for prosjektet.

I prosjektfolderen (det er viktig at du er i prosjektfolderen!) må du så kjøre

`python -m pipenv install`

Dette installerer alle de riktige pakkene du trenger i det nye virtuelle python-miljøet ditt for dette prosjektet, basert på en oppskrift som finnes i filene `Pipfile` og `Pipfile.lock`.

Så kan du kjøre følgende kommando, for å åpne Jupyter Lab i det virtuelle miljøet du nettop installerte:

`pipenv run jupyter lab`

Da skal Jupyter Lab åpnes automatisk i nettleseren din! Derifra er det bare å åpne de forskjellige Notebooksene i prosjektet, som vil guide deg videre i prosessen med å løse caset. Lykke til!