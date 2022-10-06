# Lawfred Intelligence
Doorzoek Legal Intelligence meteen vanuit uw Alfred App. De 10 meest relevante resultaten worden getoond. Op een resultaat klikken zorgt ervoor dat de Legal Intelligence link naar het document wordt geopend, dat betekent veelal het door de uitgever opgemaakte document. Als uw zoekopdracht niet meteen succesvol is kunt u ook 'view all results' klikken en wordt u naar Legal Intelligence gestuurd. 

U kunt ook de laatste 10 artikelen van uw favoriete tijdschrift zien door 'laatste [afkorting tijdschrift]' in te toetsen. 

Het is niet nodig dat u ingelogd bent via Legal Intelligence. 

![](Lawfredinaction.gif)

## Nieuw in v.1.4. Zoek naar Kamerstukken, wetten, en meer

- Typ 'lf [zoekterm]' en er wordt meteen gezocht. Kies het artikel uit dat u wilt lezen en druk Enter. U komt meteen bij de brontekst uit (veelal de door de uitgever opgemaakte PDF) 
- Typ 'laatste' voor de laatste artikelen in uw favoriete tijdschrift. 'laatste  [afkorting]'. Let goed op, dit is hoofdlettergevoelig. Controleer de afkorting van de bron via  https://www.legalintelligence.com/sources 
- Typ 'hr' en zie direct de laatste 7 dagen aan arresten van de Hoge Raad
- Typ 'phr' en zie direct de uitgevaardigde AG en PHR conclusies van de afgelopen 7 dagen (NL)
- Typ 'rs [zoekterm]' en zoek direct op Rechtspraak.nl naar uitspraken die de zoekterm hebben
- Typ 'ECLI [ECLI:NL:xxxxxxx]' en ga direct naar de uitspraak op Rechtspraak.nl 
- Typ 'curia [zoekterm]' en zoek direct op partijnaam naar HvJEU uitspraken
- Typ 'curiaz  [zoekterm]' en zoek op C-nummer van een zaak bij het HvJEU
- Typ 'wet [zoekterm]' and you'll search the wetten.overheid.nl database for any law that is in force as of this moment. 
- Typ 'kst' voor kamerstukken. U wordt dan gevraagd naar het dossiernummer. Voer dit in zonder spaties. Daarna ook eventueel een ordernummer (bijv. 3 voor de Memorie van toelichting of 2 als het gaat om het wetsvoorstel) en dan komt u direct op de website van het kamerstuk.
- Typ 'kstz' voor zoeken binnen kamerstukken zonder dat u het dossiernummer weet. Dit is vrij zoeken. 
- Typ 'ic' voor de internetconsultaties. U kunt 'ic + [search term]' gebruiken om meteen in de internetconsultaties te zoeken
- Typ 'evrm' voor de tekst van het EVRM
- Typ 'hv' voor de tekst van het Handvest



![](lawfred1-3.gif)


# Installatie 
Download de workflow via [releases](https://github.com/ABeehive/lawfred-intelligence/releases). 

U moet een Legal Intelligence account hebben en een zogenoemd client-secret. Om een workflow te draaien in Alfred is ook een Alfred Powerpack licentie nodig

## Hoe kom ik aan een client-secret 
Log in op uw Legal Intelligence account. klik dan [deze](https://www.legalintelligence.com/userprofile?opengenerateapikeylightbox=true) link. Dit genereert een client secret of vraag u om dit te doen. Kopieer deze en sla het eventjes ergens op. Het wordt niet zichtbaar opgeslagen in uw Legal Intelligence account zelf. 

## Client-id en Client-secret invoegen in workflow
Open de geimporteerde workflow in Alfred. 
Open de Environmental Variables and voeg uw ClientID in (voor mij was dit mijn emailadres) voeg ook uw Client-secret in dat u heeft gegenereerd in de stap hierboven. 

Opslaan en dan zou het moeten werken!

## Afhankelijkheden
De workflow maakt gebruik van Python libraries zoals: urllib3, requests, en xmltodict. Deze zijn als het goed is allemaal gebundeld in de workflow dus hoeven niet apart te worden geinstalleerd.  

Met het uitfaseren van python2 moest de workflow anders worden opgebouwd. Nu wordt er gebruik gemaakt van de external script functie in 'script filters'. Dit kan voor een probleem zorgen, namelijk als de shebang niet overeenkomt met de locatie van python3. 

U kunt dit controleren op de volgende wijze (hoeft niet als alles werkt)
Ga naar de terminal.app → typ: 'which python3' (zonder aanhalingstekens) en als het resultaat is : /usr/local/bin/python3. Dan hoeft u niets te doen. Als er echter iets anders staat dan moet u dit even kopieren en overal veranderen in de external scripts. 

Dat doet u als volgt: 
1. klik op de onderdelen 'script filter' in de workflow. 
2. klik op 'open file'
3. verander #!/usr/local/bin/python3 (helemaal bovenaan) door: #! + het resultaat van de vraag 'which python3' . Zorg ervoor dat #! blijft staan! 
4. Opslaan en naar de volgende. Herhaal dit voor alle 'Script Filters' in de workflow. 

Werkt het nog niet, moeten misschien toch de modules worden geinstalleerd, maar dat lijkt me niet waarschijnlijk. 


