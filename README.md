# Muffins AI Motor 🧁🤖🚗💥

Dette er et case for en maskinlæringsworkshop organisert av [BRAIN NTNU](https://brainntnu.no/) og [Fremtind Forsikring](https://www.linkedin.com/company/fremtind), den 1. mars 2023. Det er antatt at deltagerene har grunnleggende Python-kunskaper, og har installert [Anaconda](https://www.anaconda.com/products/distribution) eller Miniconda på datamskinen sin.

Hvis du ikke har Anaconda installert, følg instruksjonene under overskriften "Praktisk"

## 🤔 Introduksjon

Dette prosjektet er et git-repository som er hostet hos GitHub. Det betyr at prosjektet med alt innhold er versjonskontrollert med verktøyet [git](https://git-scm.com/) og er tilgjengelig online, som gjør det enklere for flere mennesker å samarbeide, oppdatere, og hente prosjektet fra nettet. Prosjektet inneholder nesten alt du trenger for å løse oppgaven på en grei måte.

Vi skal se på et datasett som inneholder utbetalingskrav for rapporterte skader på forsikrede kjøretøy. Det ble oppdaget at noen av disse kravene var forsøk på svindel! Vi skal lage en maskinlæringsmodell som snuser ut fremtidig muffens blant de inrapporterte kravene. Dette kalles en "binær klassifikasjonsoppgave", fordi maskinlæringsmodellen sin jobb er å dele inn kravene i to klasser, "mistenkt svindel" og "ikke mistenkt svindel". Dette kan en maskinlæringsmodell forsøke å lære seg, ved å se på hvilke fellestrekk identifiserte svindelsaker har hatt i fortiden. Men pass på, ikke all data er bra data, og noen ganger har valgene dine som maskinlæringsingeniør etiske konsekvenser for dem som blir påvirket av systemet: Greier du å identifisere og forutse ulike etiske konsekvenser basert på hvilke data du bruker, og hvordan du optimerer modellen din? Greier du å unngå diskriminering på beskyttede kategorier i [likestillings og diskrimineringslovens paragraf 6](https://lovdata.no/dokument/NL/lov/2017-06-16-51)? Hvilke konsekvenser vil det ha å stole på en unøyaktig modell, og hvordan bør man i forskjellige tilfeller bruke den for å unngå negative konsekvenser?

Radene i datasettet representerer erstatningskrav fra erstatningstager til forsikringsselskapet. Dataene vi bruker er en salig kombinasjon av kategoriske data (som bilmerke) og kontinuerlig distribuerte data (som prisen på forsikringsobjektet), og noen av kravene mangler også noe data. Det er din jobb som maskinlæringsingeniør å velge hvordan du masserer dataene. Hva er bra og dårlig data? Hvilke kolonner skal du bruke, og hvordan skal de representeres eller kombineres når du sender dem inn i modellen din? Da lønner det seg å ha kunnskap om hvilke maskinlæringsmodeller som fungerer for forskjellig data, og hvordan kan du eventuelt kan prosessere dataene for å få de til å fungere bedre med en gitt modelltype.

### 📓 Notebooks

Vi har skrevet to [Jupyter](https://jupyter.org/) Notebooks som dere kan bruke som utgangspunkt for å løse oppgavene.

`data_investigation.ipynb` inneholder delvis kode for å utforske og vaske dataene.
`maskinlæring.ipynb` inneholder delvis kode for å trene en logistisk regressor, og utforske resultatene som modellen gir.

Den logistiske regresjonen i `maskinlæring.ipynb`-notebooken krever data som er tilstrekkelig preprosessert, altså at kategoriske variabler er encodet som tall. Dere må da kjøre gjennom data_investigation-notebooken for å produsere denne dataen, og sørge for at maskinlæring-notebooken leser den riktige filen.

## 🛠️ Praktisk 

Installer Anacoda (eller miniconda) som fungerer med ditt operativsystem [her](https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html)

**NB**: Hvis du har Mac med M1 eller M2 (Apple Silicon) chip, må du installere to ekstra pakker ved å kjøre følgende kommando:  

`brew install cmake libomp`
(Denne kommandoen vil ikke fungere om du ikke har package mangeren [homebrew](https://brew.sh/) installert. Dette er et vanlig og viktig program som du kan installere med en annen kommando du kan finne på lenken, dersom det viser seg at du ikke har det)  

For å laste ned dette git-repositoriet til maskinen din kan du enten bruke kildekodeversjoneringsverktøyet [git](https://git-scm.com/), eller laste ned dette prosjektet som en zip-fil, ved å klikke på den grønne [<>CODE]-knappen du ser over denne README-filen slik den vises på github.

Hvis du har git installert kan du gå åpne terminalen din fra mappen du ønsker å lagre prosjektmappen i og kjøre denne kommandoen for å kopiere hele prosjektet til maskinen din:


```
git clone https://github.com/odaon/muffins-ai-motor.git
```

Naviger til repository mappen:
```
cd muffins-ai-motor
```

Kjør følgende kommandoer i gitt rekkefølge:  
```
conda create -y -n muffins-ai python=3.10
```

```
conda activate muffins-ai
```

```
pip install -r requirements.txt
```
Nå har du laget og aktivert et nytt virtuelt Pythonmiljø med Anaconda, som har de riktige pakkene installert. Slik kan du ha riktige pakker for prosjektet uten å påvirke andre Pythonprosjekter på maskinen din!

Kjør så:
```
jupyter lab
```

Hvis ikke Jupyter Lab åpner seg i nettleseren automatisk skal du se noe som likner på dette i terminalen:
```console
[C 2023-02-13 10:49:10.328 ServerApp] 
    
    To access the server, open this file in a browser:
        file:///home/markuhei/.local/share/jupyter/runtime/jpserver-20845-open.html
    Or copy and paste one of these URLs:
        http://localhost:8888/lab?token=ba0ff325d0687d8ac7fc8846c0f5832f11464f924d368388
     or http://127.0.0.1:8888/lab?token=ba0ff325d0687d8ac7fc8846c0f5832f11464f924d368388

```

Åpne lenken i nettleseren, så er du i gang.

## 📝 Oppgaven

Dette er en konkurranse hvor vi deler dere inn i lag. Konkurransen har tre deler for å være sikker på at selv de flinkeste skal ha noe å gjøre hele kvelden, men det er veldig bra å "bare" gjøre et ærlig forsøk på noen av oppgavene!

1. Preprosesser data slik at dere får trent en logistisk regresjonsmodell med så høy som mulig sammenlagt `ROC-AUC + Average Precission`.

2. Tren en hvilken som helst slags maskinlæringsmodell med så høy som mulig sammenlagt `ROC-AUC + Average Precission`. Dere står frie til å gjøre egne valg, men får tips om at LightGBM er et godt alternativ for denne typen data.

> NB: På oppgave 1 og 2 vil dere bli målt på et testsett i samme format som dataen dere har fått, men som dere ikke har tilgang til når dere tuner modellen og skriver preprosesseringskoden.

3. Redegjør for:
- Hvilke kolonner eller kombinasjoner av kolonner som kan være etisk uheldige å bruke, og hvorfor.
- De etiske implikasjonene av å bruke en maskinlæringsmodell til å peke ut suspekte krav og bruke det i en prosess (Tenk på hvordan modellen din sine forskjellige scoremetrikker påvirker hvor etisk den er i bruk, og hvordan den etisk kan brukes i en prosess).

**BONUS:** Lag den beste maskinlæringsmodellen dere kan som tar tilstrekkelig høyde for de etiske problemene vi møter på, og utelater problematiske data. Redegjør for en etisk måte å bruke denne maskinlæringsmodellen på i prosessen for å identifisere, stoppe eller forebygge svindel.

## 🧑‍⚖️ Etikk, likestilling, og diskriminering

Den følgende informasjonen kan være en nyttig pekepin for hvordan å jobbe med oppgave 3.

I Norge er det et krav fra Finanstilsynet

> om at det ikke skjer urimelig forskjellsbehandling mellom [...] kundegrupper

i forsikring. Det er også verdt å merke seg at

> Finanstilsynet ser at bruk av avansert analyse med økt antall forklaringsvariabler kan gi økt
nøyaktighet [...]. Det er imidlertid risiko for at bruk av detaljerte data og mer
avansert analyse kan føre til at enkelte kunder, eller kundegrupper, i praksis utelukkes fra forsikringskollektivet. [...]
> Problemstillingen er spesielt relevant for produkter med høy samfunnsnytte,
eller som kan påvirke sårbare kundegrupper særskilt.

**Likestillings- og diskrimineringsloven** er den mest grunnleggende formaliseringen av etisk praksis rund forskjelsbehandling av kunder i Norge. Her er et relevant utdrag:
>
>**§ 6. Forbud mot å diskriminere**
>
>Diskriminering på grunn av kjønn, graviditet, permisjon ved fødsel eller adopsjon, omsorgsoppgaver, etnisitet, religion, livssyn, funksjonsnedsettelse, seksuell orientering, kjønnsidentitet, kjønnsuttrykk, alder eller kombinasjoner av disse grunnlagene er forbudt. Med etnisitet menes blant annet nasjonal opprinnelse, avstamning, hudfarge og språk.
>
>Forbudet omfatter diskriminering på grunn av eksisterende, antatte, tidligere eller fremtidige forhold som nevnt i første ledd.
>
>Forbudet gjelder også hvis en person blir diskriminert på grunn av sin tilknytning til en annen person, og diskrimineringen skjer på grunn av forhold som nevnt i første ledd.
>
>Med diskriminering menes direkte eller indirekte forskjellsbehandling etter §§ 7 og 8 som ikke er lovlig etter §§ 9, 10 eller 11.
>
>
>**§ 7. Direkte forskjellsbehandling**
>
>Med direkte forskjellsbehandling menes at en person behandles dårligere enn andre blir, har blitt eller ville blitt behandlet i en tilsvarende situasjon, på grunn av forhold som nevnt i § 6 første ledd.
>
>
>**§ 8. Indirekte forskjellsbehandling**
>
>Med indirekte forskjellsbehandling menes enhver tilsynelatende nøytral bestemmelse, betingelse, praksis, handling eller unnlatelse som vil stille personer dårligere enn andre, på grunn av forhold som nevnt i § 6 første ledd.
>
>
>**§ 9. Lovlig forskjellsbehandling**
>
>Forskjellsbehandling er ikke i strid med forbudet i § 6 når den
> 
>a.	har et saklig formål
> 
>b.	er nødvendig for å oppnå formålet og
> 
>c.	ikke er uforholdsmessig inngripende overfor den eller de som forskjellsbehandles.
>
>I arbeidsforhold og ved valg og behandling av selvstendig næringsdrivende og innleide arbeidstakere er direkte forskjellsbehandling på grunn av kjønn, etnisitet, religion, livssyn, funksjonsnedsettelse, seksuell orientering, kjønnsidentitet og kjønnsuttrykk bare tillatt hvis denne egenskapen har avgjørende betydning for utøvelsen av arbeidet eller yrket, og vilkårene i første ledd er oppfylt.
>
>Aldersgrenser som følger av lov eller forskrift, og fordelaktige priser på grunn av alder, er ikke i strid med forbudet i § 6.
