# Lawfred Intelligence
Search Legal Intelligence directly from your Alfred App. 
It will display the 10 most relevant results. Clicking a result will open the Legal Intelligence link to the document. If your desired result isn't there, there is also a 'view all results', which directs you to your search query on Legal Intelligence. 
You can also view the latest articles of a particular journal if you know the abbreviation by typing 'laatste [abbreviation]'
You need not be logged into Legal Intelligence.

![](Lawfredinaction.gif)

## New features in v 1.4 - Search laws, parlementary documentation (kamerstukken), and reveal latest Hoge Raad rulings and AG opinions
No need to install anything for this

Type 'wet [search term]' and you'll search the wetten.overheid.nl database for any law that is in force as of this moment. 
Type 'hr' en zie direct de laatste 7 dagen aan arresten van de Hoge Raad
Type 'phr' en zie direct de uitgevaardigde AG en PHR conclusies van de afgelopen 7 dagen (NL)
Typ 'rs [search term]' en zoek direct op Rechtspraak.nl naar uitspraken die de zoekterm hebben
Typ 'ECLI [ECLI:NL:xxxxxxx]' en ga direct naar de uitspraak op Rechtspraak.nl 
Typ 'curia [search term]' en zoek direct op partijnaam naar HvJEU uitspraken
Type 'curiaz  [search term]' en zoek op C-nummer van een zaak bij het HvJEU

Typ 'kst' voor kamerstukken. U wordt dan gevraagd naar het dossiernummer. Voer dit in zonder spaties. Daarna ook eventueel een ordernummer (bijv. 3 voor de Memorie van toelichting of 2 als het gaat om het wetsvoorstel) en dan komt u direct op de website van het kamerstuk.
Typ 'kstz' voor zoeken binnen kamerstukken zonder dat u het dossiernummer weet. Dit is vrij zoeken. 

Typ 'ic' voor de internetconsultaties. U kunt 'ic + [search term]' gebruiken om meteen in de internetconsultaties te zoeken
Typ 'evrm' voor de tekst van het EVRM
Typ 'hv' voor de tekst van het Handvest


![](lawfred1-3.gif)


# Installation 
Download the workflow from [releases](https://github.com/ABeehive/lawfred-intelligence/releases). 

You require a Legal Intelligence account and a client-secret.
It also requires an Alfred Powerpack license.

## Getting a client-secret 
Log into your Legal Intelligence account. Then simply click [this link](https://www.legalintelligence.com/userprofile?opengenerateapikeylightbox=true) and generate a client secret. Copy this somewhere as you'll need it for your authorisation token, and it is not displayed in your account. 

## Insert your client-secret and client-ID in workflow
Open the imported workflow in Alfred. 
Open the Environmental Variables and insert your ClientID (for me it was my university email address) and your ClientSecret that you generated earlier.

Save and that ought to do it!

## Dependencies
The workflow requires the Python requests module and xmltodict module which are both bundled in the released workflow so no need to install it separately. So this is only relevant if you create the workflow using the .plist file in this repository. 


# TODO
- [X] ~~Fix bug that less than 10 results won't be displayed. (has to do with the use of count function)~~
- [x] ~~Include a delay, so that api is not called for each letter that is typed~~
- [x] ~~Find a way that login is not required in browser for it to work~~
- [x] ~~Find a way to automatically generate authorisation token~~
- [x] ~~Insert a link to all the search results in Legal Intelligence itself~~
- [ ] Searching latest issue of a journal now requires the correct use of capitals for the abbreviation. I want to make it irrelevant whether the user types in the correct capitalisation in the abbreviation.
