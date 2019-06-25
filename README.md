# Lawfred Intelligence
Search Legal Intelligence directly from your Alfred App. 
It will display the 10 most relevant results. Clicking a result will open the Legal Intelligence link to the document. If your desired result isn't there, there is also a 'view all results', which directs you to your search query on Legal Intelligence. 
You can also view the latest articles of a particular journal if you know the abbreviation by typing 'laatste [abbreviation]'
You need not be logged into Legal Intelligence.

![](Lawfredinaction.gif)

## New features in v 1.3 - Search laws and reveal latest Hoge Raad rulings and AG opinions
No noeed to install anything for this

Use 'wet [query]' to query the law you're searching for. Abbreviations are allowed
Use 'hr' to view the last 7 days of Hoge Raad rulings
Use 'phr' to view the last 7 days of AG Opinions

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
